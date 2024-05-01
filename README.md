# Part1
We choose the bug in the method `reverseInPlace` in the java file ArrayExamples.


1. A failure-inducing input:
   ```
   @Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3,4,5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5,4,3,2,1 }, input1);
	}  
   ```
  In this case, the failure inducing input is `input1={1,2,3,4,5}`
2. An input that doesn't induce a failure:
    ```
   @Test 
	public void testReverseInPlace2() {
    int[] input1 = { 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
	}
   ```
  In this case, `input1={1}` does not induce a failure.

3. The symptom:
   ![Image]()
   ![Image](https://github.com/yigegong/cse15l-lab-report3/assets/139932435/fbc7527c-d624-409f-90d7-be609fb16ab3)

4. The bug:
    ```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
    ```
   After it's fixed:
   ```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
  ```

5. Briefly describe (2-3 sentences) why the fix addresses the issue.
The bug is this line: `arr[i] = arr[arr.length - i - 1]`, which goes wrong for the iterations after arr.length/2 and copies the original elements back.

To fix this problem, we only iterate for half of the length, saving the element in the first half to `temp`, passing `arr[arr.length - i - 1]` to `arr[i]`, and passing the value of `arr[i]` to `arr[arr.length - i - 1]` through `temp`. By swaping values in pairs, we successfully reverse the array.
# Part2
