Download Link: https://assignmentchef.com/product/solved-coen20-lab3-copying-data-quickly
<br>



<em>Topics: Load and store instructions, unrolling loops, the .rept directive, comparing execution times.      </em>

Create five functions in ARM Cortex-M4 assembly all contained in a single source code file. Each function copies 512 bytes of data from one array to another.

Each function should use the .REPT and .ENDR directives shown in Listing 4-1 to copy the data without a loop using a straight-line sequence of instructions. The main program (download <a href="http://www.cse.scu.edu/~dlewis/book3/labs/Lab3Main.c">here</a><a href="http://www.cse.scu.edu/~dlewis/book3/labs/Lab3Main.c">)</a> will display the relative execution time of the three functions.

<h1>void UseLDRB(void *dst, void *src)</h1>

Copy 1 byte at a time using LDRB and STRB, and optimize the execution time by updating the address using the Post-Indexed addressing mode shown in Table 4-6.

<h1>void UseLDRH(void *dst, void *src)</h1>

Copy 2 bytes at a time using LDRH and STRH, and optimize the execution time by updating the address using the Post-Indexed addressing mode shown in Table 4-6.

<h1>void UseLDR(void *dst, void *src)</h1>

Copy 4 bytes at a time using LDR and STR, and optimize the execution time by updating the address using the Post-Indexed addressing mode shown in Table 4-6.

<h1>void UseLDRD(void *dst, void *src)</h1>

Copy 8 bytes at a time using LDRD and STRD, and optimize the execution time by updating the address using the Post-Indexed addressing mode shown in Table 4-6.

<h1>void UseLDM(void *dst, void *src)</h1>

Copy 32 bytes at a time using LDMIA and STMIA, and optimize the execution time by updating the address using the write-back flag (!) shown in Table 4-7.

If your code is correct, the display should look similar to the image at right with each function’s execution time shown in clock cycles at the top of each bar graph. (Your numbers may differ, and the bar graph of an incorrect copy will be displayed in solid red.)

The bar graph labeled “mcpy” shows the clock cycle count for the library function memcpy, and the graph labeled “DMA” is the clock cycle count for a function provided in the main program that uses direct memory access. Note that once initialized by software, DMA transfers have the advantage of being independent of instruction execution so that both can continue concurrently.