Download Link: https://assignmentchef.com/product/solved-gpgpu-assignment-3-opencl-matrix-multiplication
<br>



Create an OpenCL program that takes as inputs two square matrices A and B with dimension (40 x 40) and perform the multiplication of the two matrices to create matrix C = A x B.

Requirements:

<ol>

 <li>For the purpose of easy grading and error checking, please define N and BLOCK_SIZE to 40 and 1 respectively, and initialize your input matrices A and B as below (“inputMatrix1” and “inputMatrix2” stand for A and B, “results” stands for C):</li>

</ol>

…

<ol start="2">

 <li>Write your kernel function in the offline mode, i.e., creating a separate .cl file for your kernel function other than writing it as a string inside the main program. You can load your .cl kernel file by calling loadProgSource(…) function. (Refer to Sample Code in Lecture 14 “vecSquare_2.cpp”) .</li>

 <li>Retrieve the latest compilation results embedded in the program object by clGetBuildProgramInfo(). (Refer to page 14 in Lecture 14).</li>

 <li>In your kernel function, decompose the multiplication into small work-groups working in parallel, i.e., you need to specify both the total number of work-items (global dimensions) and the number of work-items per work-group (local dimensions) and pass them to clEnqueueNDRangeKernel(…), e.g.,</li>

</ol>




<ol start="5">

 <li>Use event to profile the kernel execution time. (Refer to Page 60 on</li>

</ol>

Lecture 15, but using CL_PROFILING_COMMAND_START and CL_PROFILING_COMMAND_END in clGetEventProfilingInfo(…) calls instead.)

<ol start="6">

 <li>Gradually increase the BLOCK_SIZE from 1 to 2, 4, 8, 10, and 20, respectively, run your code again, record your kernel execution time from event profiling each time, and finally draw a time vs. BLOCK_SIZE chart to show the trend, e.g,</li>

</ol>


