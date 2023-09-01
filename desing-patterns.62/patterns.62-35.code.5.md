# Patterns (62) | Python Examples

## Concurrency Patterns (8)

### 1. Active Object

```python
import threading
import time

class ActiveObject:
    def __init__(self):
        self.queue = []

    def schedule(self, func, args):
        self.queue.append((func, args))

    def run(self):
        while self.queue:
            func, args = self.queue.pop(0)
            func(*args)

def print_message(message):
    print(f"Message: {message}")

active_object = ActiveObject()
active_object.schedule(print_message, ("Hello",))
active_object.schedule(print_message, ("World",))

# Ejecutar el active object
active_object.run()
```

### 2. Monitor Object

```python
import threading

class MonitorObject:
    def __init__(self):
        self.lock = threading.Lock()

    def do_something(self):
        with self.lock:
            print("Thread is inside the monitor object")

monitor = MonitorObject()

def thread_function():
    monitor.do_something()

threads = [threading.Thread(target=thread_function) for _ in range(5)]

for thread in threads:
    thread.start()

for thread in threads:
    thread.join()
```

### 3. Half-Sync/Half-Async

```python
import threading

class WorkerThread(threading.Thread):
    def __init__(self, task_queue, result_queue):
        super().__init__()
        self.task_queue = task_queue
        self.result_queue = result_queue

    def run(self):
        while True:
            task = self.task_queue.get()
            if task is None:
                break
            result = task()
            self.result_queue.put(result)

def do_work():
    return "Work done by thread {}".format(threading.current_thread().ident)

task_queue = queue.Queue()
result_queue = queue.Queue()
threads = [WorkerThread(task_queue, result_queue) for _ in range(5)]

for thread in threads:
    thread.start()

for _ in range(10):
    task_queue.put(do_work())

# Add None to the task queue to signal threads to exit
for _ in threads:
    task_queue.put(None)

for thread in threads:
    thread.join()

while not result_queue.empty():
    result = result_queue.get()
    print(result)
```

### 4. Thread Pool

```python
import concurrent.futures

def task_function(task_id):
    print(f"Executing task {task_id}")
    return f"Task {task_id} completed"

# Crear un ThreadPoolExecutor con 3 hilos
with concurrent.futures.ThreadPoolExecutor(max_workers=3) as executor:
    tasks = [executor.submit(task_function, i) for i in range(5)]

    for future in concurrent.futures.as_completed(tasks):
        result = future.result()
        print(result)
```

### 5. Double-Checked Locking

```python
import threading

class Singleton:
    _instance = None
    _lock = threading.Lock()

    def __new__(cls):
        if cls._instance is None:
            with cls._lock:
                if cls._instance is None:
                    cls._instance = super(Singleton, cls).__new__(cls)
        return cls._instance

# Test de Singleton
instance1 = Singleton()
instance2 = Singleton()
print(instance1 is instance2)  # Ambos son la misma instancia
```

### 6. Thread-Specific Storage

```python
import threading

def thread_function(value):
    storage = threading.local()
    storage.value = value
    print(f"Thread-local value: {storage.value}")

threads = [threading.Thread(target=thread_function, args=(i,)) for i in range(3)]

for thread in threads:
    thread.start()

for thread in threads:
    thread.join()
```

### 7. Balking Pattern

```python
import threading
import time

class AutoSaveThread(threading.Thread):
    def __init__(self, data):
        super().__init__()
        self.data = data
        self.saved = False

    def run(self):
        while True:
            if not self.saved:
                self.save_data()
                self.saved = True
            time.sleep(1)

    def save_data(self):
        print(f"Saving data: {self.data}")

data_to_save = "Important data"
auto_save_thread = AutoSaveThread(data_to_save)
auto_save_thread.start()

# Simulación de cambio de datos después de 3 segundos
time.sleep(3)
data_to_save = "Modified data"
auto_save_thread.saved = False

# Detener el hilo después de 5 segundos
time.sleep(5)
auto_save_thread.join()
```

### 8. Barrier Pattern

```python
import threading

barrier = threading.Barrier(3)  # Se espera la llegada de 3 hilos

def worker_thread():
    print(f"Thread {threading.current_thread().ident} is waiting at the barrier")
    barrier.wait()
    print(f"Thread {threading.current_thread().ident} has passed the barrier")

threads = [threading.Thread(target=worker_thread) for _ in range(3)]

for thread in threads:
    thread.start()

for thread in threads:
    thread.join()

print("All threads have passed the barrier")
```
