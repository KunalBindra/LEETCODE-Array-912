# LEETCODE-Array-912
The `Solution` class sorts an array of integers using a priority queue (min-heap). Here's a dry run explanation for the method `sortArray`:

1. **Initialize Result Array and Priority Queue:**
   ```java
   int[] res = new int[nums.length];
   PriorityQueue<Integer> pq = new PriorityQueue<>();
   ```

2. **Populate Priority Queue:**
   ```java
   for (int i = 0; i < nums.length; i++) {
       pq.offer(nums[i]);
   }
   ```
   This loop inserts all elements of the input array `nums` into the priority queue `pq`.

3. **Extract Sorted Elements:**
   ```java
   int index = 0;
   while (!pq.isEmpty()) {
       res[index] = pq.poll();
       index++;
   }
   ```
   This loop removes the smallest element from the priority queue (due to the nature of the min-heap) and places it into the result array `res`. The index is incremented after each insertion.

4. **Return Result Array:**
   ```java
   return res;
   ```

### Example Dry Run

Consider the input array: `nums = [5, 2, 8, 1, 3]`.

1. **Initialization:**
   - `res = [0, 0, 0, 0, 0]`
   - `pq` (empty priority queue)

2. **Populate Priority Queue:**
   - After inserting 5: `pq = [5]`
   - After inserting 2: `pq = [2, 5]`
   - After inserting 8: `pq = [2, 5, 8]`
   - After inserting 1: `pq = [1, 2, 8, 5]`
   - After inserting 3: `pq = [1, 2, 8, 5, 3]`

3. **Extract Sorted Elements:**
   - Extract 1: `res = [1, 0, 0, 0, 0]`, `pq = [2, 3, 8, 5]`
   - Extract 2: `res = [1, 2, 0, 0, 0]`, `pq = [3, 5, 8]`
   - Extract 3: `res = [1, 2, 3, 0, 0]`, `pq = [5, 8]`
   - Extract 5: `res = [1, 2, 3, 5, 0]`, `pq = [8]`
   - Extract 8: `res = [1, 2, 3, 5, 8]`, `pq` is empty

4. **Return Result:**
   - Final sorted array: `res = [1, 2, 3, 5, 8]`

The method successfully sorts the input array using a priority queue.
