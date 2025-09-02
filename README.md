# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   2000:7F               |    2004:7F               |
|   2001:04               |    2005:79               |
|   2002:00               |    2006:00               |
|   2003:75               |                          |

#### Manual Calculations

![aksum_addition masm](https://github.com/user-attachments/assets/9d568de4-2250-44ae-b772-acde7d2ae9fe)


---

## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="622" height="384" alt="aksum_additiom_asm" src="https://github.com/user-attachments/assets/fe33e968-0d0e-4741-9914-b4740a18ae69" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,1500H
MOV CL,00H
MOV [SI],1234H
MOV [SI+02H],1230H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1500: 34              |    1504: 04              |
|   1501: 12              |    1505: 00              |
|   1502: 30              |    1506: 00              |
|   1503: 12              |    1507: 00              |

#### Manual Calculations

![aksub_masm](https://github.com/user-attachments/assets/22bbc07c-b518-43e8-8447-7f487d2c76a9)


---


## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="638" height="396" alt="aksub_asm" src="https://github.com/user-attachments/assets/c1169bc8-26ef-4072-aeb6-bde60acf7b77" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,1200H
MOV DX,0000H
MOV [SI],1234H
MOV [SI+02H],5678H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1200: 34              |    1204: 60              |
|   1201: 12              |    1205: 00              |
|   1202: 78              |    1206: 26              |
|   1203: 56              |    1207: 06              |

#### Manual Calculations

![akmul masm](https://github.com/user-attachments/assets/2993f67b-df2b-498b-8e10-796e39c234df)


---

## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="628" height="398" alt="akmul asm" src="https://github.com/user-attachments/assets/5fa94848-157b-40f4-bca0-0df7c8ab1852" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,1200H
MOV DX,0000H
MOV [SI],0225H
MOV [SI+02H],0110H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|    1200: 25             |     1204: 02             |
|    1201: 02             |     1205: 00             |
|    1202: 10             |     1206: 05             |
|    1203: 01             |     1207: 00             |

#### Manual Calculations

![akdiv_masm](https://github.com/user-attachments/assets/502697bb-56f3-42fd-b3d3-fdf2cc5feb6e)


---
## OUTPUT FROM MASM SOFTWARE

<img width="628" height="378" alt="akdiv_asm" src="https://github.com/user-attachments/assets/2f8d016f-d7c8-4c0d-8d5b-5cd1598108fe" />




## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
