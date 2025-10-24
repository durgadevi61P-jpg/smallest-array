# smallest-array
AIM

To write and execute an 8086 assembly language program to find the smallest number in an array of N elements using conditional jump instructions.

APPARATUS REQUIRED

* Personal Computer with MASM Software

ALGORITHM

1.Start the program.

2.Initialize the data segment.

3.Load the count value (5) into CX (this represents how many array elements to process).

4.Load BL with a large initial value (here 79h) so that any array value will be smaller than it.

5.Load the starting address of the array into SI.

6.Repeat the following steps for each element in the array:

      i)Load the current array element into AL.
      
      ii)Compare AL with BL.
      
      iii)If AL is less than BL, then update BL = AL (so BL always holds the smallest number found so far).
      
      iv)Move to the next element by incrementing SI.
      
      v)Decrease CX and repeat until CX becomes zero.
      
7.After the loop ends, BL contains the smallest number.

8.Store BL into the memory variable result.

9.Convert the result to ASCII and print it using DOS interrupt.

10.Terminate the program.

PROGRAM
```
dosseg
.model small
.stack 100h
.data
          array db   5,6,7,8,9
          result db  ?
.code
main proc
           mov ax,@data
           mov ds,ax
           mov cx,5
           mov bl,79h
           lea si,array
           l1:
           mov al,[si]
           cmp al,bl
           jge l2
           mov bl,al
           l2:
           inc si
           dec cx
           jnz l1
           mov result,bl
           mov dl,result
           add dl,48 
           mov ah,2
           int 21h
          mov ah,4ch
          int 21h
main endp
end main
```

OUTPUT IMAGE FROM MASM SOFTWARE

![WhatsApp Image 2025-10-24 at 20 24 35_4d41b77c](https://github.com/user-attachments/assets/97125606-8976-4d06-9288-2411c66f7690)

![WhatsApp Image 2025-10-24 at 20 24 10_ebffb529](https://github.com/user-attachments/assets/60f6a9f3-7145-40fc-b0ab-15895a9ac256)

![WhatsApp Image 2025-10-24 at 20 24 47_6bcd124e](https://github.com/user-attachments/assets/babd02f5-1114-4767-8642-8015da07e0af)


RESULT

Thus, the 8086 assembly language program was executed successfully. The program compared each element of the array and determined the smallest value.







