# std::map

>Map is useful when data has key & value. (like database) <br> But map can be expensive, because of its implementation. <br>

Basic utilization. (Insert & Get);

```cpp
map<string, string> basicMap;
basicMap.emplace(pair<string, string>("Hello", "Hello world!"));
cout << basicMap.at("Hello") << endl;
```
****************************
### map implementation.
* std::map
    * [RED-BLACK-TREE](https://en.wikipedia.org/wiki/Red%E2%80%93black_tree)
    * Self balancing tree like AVL tree.
    * insert / delete complexity : O(lgN)
    * Self balancing complexity  : O(1) (AVL tree's complexity is O(lgN))
    * But, look-up slowly than AVL tree.

### conclusions..
Use std::map when...
* Lots of insertion & deletion, but rarely search.
* When search something a lot of time, but rarely insert & delete, you can use hash_map.