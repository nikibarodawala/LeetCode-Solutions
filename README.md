# LeetCode-Solutions
763. Partition Labels Problems

Algorithm - To solve this problem, we will use a two pointer solution.

Steps:
1. First we create a hashmap of the last index of each unique character in the string. This is done by looping through the string and storing the index at which each letter occurs. If a letter is repeated, the hash will update with the greater index and only the last occurrence will be saved.

2. Next comes the two pointer part. First we will initialize our partitions array (this is what we will be returning) and we initialize our two pointers to the start of the string (set end and start to 0).

3. Then we loop through the string, setting the end pointer. The end pointer is the bigger value between the index we are on, and the last index of the character we are on (use the hashmap!).

4. Next we compare the position of our end pointer against where we are in terms of iterating over the string. If the current index is not the same as the end index, we have to keep moving and do nothing.

5. However, if the end and current index are the same then we must be at the end of a partition. Basically, this character wont appear again so you should make a cut in the string to ensure we get the maximum number of partitions.

6. To make a cut, push the length of the segment into the partitions array. Then we update our start pointer to one after the end of the last partition.

7. After the end of the loop, we simply return the partitions array.
