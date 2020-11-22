# Depth first search \(Aka DFS\)

Dfs algorithm makes sure every vertex in a certain graph is explored & doesn't care about the shortest path like Bfs does.  We have to make sure not to repeat a vertex.  There would be backtracing though as the goal is to reach all vertices possible.  Dfs is good for finding out if there is actually path from x to y.

**Recursive template:**

```javascript
function DFS(cur, target, visited) {
    if(cur === target) return true
    const neighbours = // of cur, this implementation can vary
    for(let next of neighbours) {
        if(!visited.has(next)) {
            visited.add(next)
            if(DFS(next, target, visited)) return true
        }
    }
    return false
}
```

**Non-recursive template:**

```javascript
function DFS(root, target) {    
    const visited = new Set()
    const stack = []
    const result = []
    stack.push(root)
    while(stack.length) {
        const cur = stack.pop()  // Dfs uses stacks as opposed to queues in Bfs
        result.push(cur)
        if(cur === target) return [result, true]
        const neighbours = // of cur, this implementation can vary
        for(let next of neighbours) {
            if(!visited.has(next) {
                visited.add(next)
                stack.push(next)
            }
        }
    }
    return [result, false]
}
```

