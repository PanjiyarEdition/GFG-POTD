# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Design a data structure that works like an LRU (Least Recently Used) Cache. The cache should have the following operations:

GET x: Return the value associated with key x if it exists in the cache. Otherwise, return -1.
PUT x y: Set the value of key x to y. If the key is already present, update its value. If the cache reaches its capacity, remove the least recently used item before inserting the new item.


# 📝Code ⬇:-



# Java
```java []
class LRUCache {
    private int capacity;
    private LinkedHashMap<Integer, Integer> cache;

    LRUCache(int cap) {
        this.capacity = cap;
        this.cache = new LinkedHashMap<>(cap, 0.75f, true) {
            protected boolean removeEldestEntry(Map.Entry<Integer, Integer> eldest) {
                return size() > capacity;
            }
        };
    }
    public int get(int key) {
        return cache.getOrDefault(key, -1);
    }
    public void put(int key, int value) {
        cache.put(key, value);
    }
}

```

# C++
``` cpp []

class LRUCache {
    int capacity;
    list<pair<int, int>> cache;
    unordered_map<int, list<pair<int, int>>::iterator> map;
public:
    LRUCache(int cap) : capacity(cap) {}
    int get(int key) {
        if (!map.count(key)) return -1;
        cache.splice(cache.begin(), cache, map[key]); // Move the accessed node to the front
        return map[key]->second;
    }
    void put(int key, int value) {
        if (map.count(key)) cache.splice(cache.begin(), cache, map[key]), map[key]->second = value;
        else {
            if (cache.size() == capacity) map.erase(cache.back().first), cache.pop_back();
            cache.emplace_front(key, value), map[key] = cache.begin();
        }
    }
};
```

# Python
``` python []
from collections import OrderedDict

class LRUCache:
    def __init__(self, cap):
        self.cap = cap
        self.cache = OrderedDict()

    def get(self, key):
        if key not in self.cache:
            return -1
        self.cache.move_to_end(key)
        return self.cache[key]

    def put(self, key, value):
        if key in self.cache:
            self.cache.move_to_end(key)
        self.cache[key] = value
        if len(self.cache) > self.cap:
            self.cache.popitem(last=False)    
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
