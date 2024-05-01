![3761714543588_ pic](https://github.com/yigegong/cse15l-lab-report3/assets/139932435/deb34c18-23be-4a15-a418-fdc5bcb8fce1)# Part1
We choose the bug in the method `reverseInPlace` in the java file ArrayExamples.


1. A failure-inducing input:
   `@Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3,4,5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5,4,3,2,1 }, input1);
	}`   
  In this case, the failure inducing input is `input1={1,2,3,4,5}`
2. An input that doesn't induce a failure:
   `@Test 
	public void testReverseInPlace2() {
    int[] input1 = { 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
	}`
  In this case, `input1={1}` does not induce a failure.

3. The symptom, as the output of running the two tests above (provide it as a screenshot -- one test should pass, one test should fail).
   
7. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown).
8. Briefly describe (2-3 sentences) why the fix addresses the issue.
# Part2
