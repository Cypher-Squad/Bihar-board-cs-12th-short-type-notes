# 📚 Bihar Board Class 12 — Computer Science Exam Notes
### ⚡ Fast Revision Notes | Exam Ready | Simple English

> **Tip:** Ctrl+F se koi bhi topic dhundho. All important definitions, examples & 5-mark answers ready!

---

## 📋 TABLE OF CONTENTS
1. [SQL (Most Important)](#1-sql-most-important)
2. [Networking](#2-networking)
3. [C++ Basics](#3-c-basics)
4. [Data Structures](#4-data-structures)
5. [Boolean Algebra](#5-boolean-algebra)
6. [MCQ Quick Revision](#6-mcq-quick-revision)

---

---

# 1. SQL (Most Important)

## 🔑 What is SQL?
- **SQL = Structured Query Language**
- Used to communicate with databases
- SQL is used to **store, retrieve, update, delete** data

---

## 📌 SQL Commands — 2 Types

### DDL — Data Definition Language
> **DDL = Commands that DEFINE/CREATE the structure of database**

| Command | Work |
|---------|------|
| `CREATE` | Create new table |
| `DROP` | Delete table permanently |
| `ALTER` | Change table structure |
| `TRUNCATE` | Delete all records (keep table) |

### DML — Data Manipulation Language
> **DML = Commands that MANIPULATE/change the data inside table**

| Command | Work |
|---------|------|
| `INSERT` | Add new data |
| `UPDATE` | Modify existing data |
| `DELETE` | Remove data |
| `SELECT` | View/retrieve data |

---

## 📌 Data Types in SQL

| Data Type | Meaning | Example |
|-----------|---------|---------|
| `INT` | Whole numbers | 10, 25, 100 |
| `VARCHAR(n)` | Variable-length text | 'Rahul', 'Delhi' |
| `CHAR(n)` | Fixed-length text | 'M', 'YES' |
| `FLOAT` | Decimal numbers | 9.5, 3.14 |
| `DATE` | Date values | '2024-01-15' |

> **Difference: CHAR vs VARCHAR**
> - `CHAR(10)` always takes 10 spaces even if you store 3 characters
> - `VARCHAR(10)` takes only as much space as needed (max 10)

---

## 📌 CREATE TABLE Command

```sql
CREATE TABLE Student (
    RollNo INT,
    Name VARCHAR(30),
    Marks FLOAT,
    Class CHAR(5)
);
```
**Explanation:**
- Creates a table called `Student`
- 4 columns: RollNo, Name, Marks, Class
- Each column has a data type

---

## 📌 INSERT Command

```sql
-- Insert one row
INSERT INTO Student VALUES (1, 'Rahul', 85.5, '12th');

-- Insert specific columns
INSERT INTO Student (RollNo, Name) VALUES (2, 'Priya');
```

---

## 📌 SELECT Command (Most Asked!)

```sql
-- Select all columns
SELECT * FROM Student;

-- Select specific columns
SELECT Name, Marks FROM Student;

-- With condition (WHERE)
SELECT * FROM Student WHERE Marks > 60;

-- With ORDER BY
SELECT * FROM Student ORDER BY Marks DESC;

-- With LIKE (search)
SELECT * FROM Student WHERE Name LIKE 'R%';
```

### WHERE Operators:
| Operator | Meaning |
|----------|---------|
| `=` | Equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal |
| `LIKE 'R%'` | Starts with R |
| `LIKE '%a'` | Ends with a |
| `BETWEEN 50 AND 80` | In range |
| `IN (70, 80, 90)` | In list |

---

## 📌 UPDATE Command

```sql
-- Update all rows
UPDATE Student SET Marks = 90;

-- Update specific row
UPDATE Student SET Marks = 95 WHERE RollNo = 1;

-- Update multiple columns
UPDATE Student SET Marks = 88, Class = '12A' WHERE Name = 'Rahul';
```

---

## 📌 DELETE Command

```sql
-- Delete specific row
DELETE FROM Student WHERE RollNo = 1;

-- Delete all rows (table remains)
DELETE FROM Student;
```

---

## 📌 DROP vs DELETE vs TRUNCATE

| | DROP | DELETE | TRUNCATE |
|--|------|--------|----------|
| What deletes? | Entire table | Specific/all rows | All rows |
| Table exists after? | ❌ No | ✅ Yes | ✅ Yes |
| Can use WHERE? | ❌ No | ✅ Yes | ❌ No |
| Type | DDL | DML | DDL |

---

## 📌 ALTER Command

```sql
-- Add new column
ALTER TABLE Student ADD Address VARCHAR(50);

-- Remove column
ALTER TABLE Student DROP COLUMN Address;

-- Modify data type
ALTER TABLE Student MODIFY Marks INT;
```

---

## ⭐ 5-Mark Answer: Explain DDL and DML with examples

**DDL (Data Definition Language):**
DDL commands are used to define the structure or schema of a database. These commands work on the table structure itself, not on the data.

Main DDL Commands:
1. `CREATE` — Creates a new table. Example: `CREATE TABLE Student (RollNo INT, Name VARCHAR(30));`
2. `DROP` — Permanently deletes a table along with all its data.
3. `ALTER` — Modifies the structure of an existing table (add/remove columns).
4. `TRUNCATE` — Deletes all records from a table but keeps the table structure.

**DML (Data Manipulation Language):**
DML commands are used to manipulate the data stored inside tables.

Main DML Commands:
1. `INSERT` — Adds new records. Example: `INSERT INTO Student VALUES (1, 'Rahul');`
2. `SELECT` — Retrieves data. Example: `SELECT * FROM Student WHERE Marks > 60;`
3. `UPDATE` — Modifies existing records. Example: `UPDATE Student SET Marks = 90 WHERE RollNo = 1;`
4. `DELETE` — Removes records. Example: `DELETE FROM Student WHERE RollNo = 1;`

**Key Difference:** DDL changes the *structure*, DML changes the *data*.

---

---

# 2. Networking

## 🔑 What is a Network?
- **Network = Two or more computers connected to share data/resources**
- Allows sharing of files, printers, internet

---

## 📌 Types of Networks

### LAN — Local Area Network
- **Small area** — one building, school, office
- Fast speed, less expensive
- Example: School computer lab network

### MAN — Metropolitan Area Network
- **City-wide** network
- Connects multiple LANs in a city
- Example: Cable TV network in a city

### WAN — Wide Area Network
- **Very large area** — countries, continents
- Uses telephone lines, satellites
- Example: **Internet** is the largest WAN

| | LAN | MAN | WAN |
|-|-----|-----|-----|
| Area | Small (1 building) | Medium (city) | Large (countries) |
| Speed | High | Medium | Low |
| Cost | Low | Medium | High |
| Example | School lab | City cable | Internet |

---

## 📌 Network Topologies

> **Topology = The physical arrangement/layout of computers in a network**

### 1. Star Topology ⭐
- All computers connected to a **central hub/switch**
- If one computer fails → others still work
- If hub fails → whole network fails
- **Most commonly used** in offices

### 2. Bus Topology 🚌
- All computers connected to a **single cable (backbone)**
- If main cable fails → whole network fails
- Simple and cheap
- Used in small networks

### 3. Ring Topology 💍
- Computers connected in a **circular loop**
- Data travels in one direction
- If one computer fails → network breaks (in simple ring)

| Topology | Shape | Failure Point | Cost |
|----------|-------|---------------|------|
| Star | Star | Central Hub | Medium |
| Bus | Line | Main Cable | Low |
| Ring | Circle | Any one node | Medium |

---

## 📌 OSI Model (7 Layers)

> **OSI = Open Systems Interconnection**
> **OSI model = A standard that describes how data travels from one computer to another**

```
Layer 7 — Application    → User interface (HTTP, FTP, SMTP)
Layer 6 — Presentation   → Data format, encryption
Layer 5 — Session        → Opens/closes sessions
Layer 4 — Transport      → Reliable delivery (TCP, UDP)
Layer 3 — Network        → Routing, IP addresses
Layer 2 — Data Link      → MAC address, error detection
Layer 1 — Physical       → Actual cables, signals
```

**Easy trick to remember (top to bottom):**
> **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing

---

## 📌 Protocols

> **Protocol = A set of rules for communication between computers**

| Protocol | Full Form | Use |
|----------|-----------|-----|
| HTTP | HyperText Transfer Protocol | Web browsing |
| HTTPS | HTTP Secure | Secure web browsing |
| FTP | File Transfer Protocol | Transfer files |
| SMTP | Simple Mail Transfer Protocol | Send emails |
| POP3 | Post Office Protocol | Receive emails |
| TCP/IP | Transmission Control Protocol/Internet Protocol | Internet communication |
| DNS | Domain Name System | Convert domain to IP |

---

## 📌 Transmission Media

> **Transmission Media = The physical path through which data travels**

### Wired (Guided) Media:
1. **Twisted Pair Cable** — Cheapest, used in telephone lines
2. **Coaxial Cable** — TV cable, faster than twisted pair
3. **Optical Fiber** — Fastest, uses light signals, most expensive

### Wireless (Unguided) Media:
1. **Radio Waves** — WiFi, Bluetooth
2. **Microwaves** — Satellite communication
3. **Infrared** — TV remote, short range

---

## ⭐ 5-Mark Answer: Explain OSI Model

The OSI (Open Systems Interconnection) model is a conceptual framework that describes how data is transmitted between two computers over a network. It has **7 layers**, each with a specific function.

1. **Physical Layer (Layer 1):** Deals with physical transmission of data — cables, signals, voltages. Transmits raw bits (0s and 1s).

2. **Data Link Layer (Layer 2):** Provides error-free transfer of data between two directly connected nodes. Uses MAC addresses.

3. **Network Layer (Layer 3):** Handles routing of data from source to destination using IP addresses.

4. **Transport Layer (Layer 4):** Ensures complete data transfer. Protocols: TCP (reliable) and UDP (fast but unreliable).

5. **Session Layer (Layer 5):** Manages sessions — opening, maintaining, and closing communication sessions.

6. **Presentation Layer (Layer 6):** Translates data formats, handles encryption and compression.

7. **Application Layer (Layer 7):** Closest to the user. Provides services like web browsing (HTTP), email (SMTP), file transfer (FTP).

---

---

# 3. C++ Basics

## 📌 Structure of a C++ Program

```cpp
#include <iostream>       // Header file
using namespace std;      // Standard namespace

int main() {              // Main function — program starts here
    cout << "Hello!";     // Output statement
    return 0;             // End of program
}
```

**Parts of C++ Program:**
1. **Header Files** — Include library files (`#include <iostream>`)
2. **Namespace** — `using namespace std` — avoids writing `std::` every time
3. **main() function** — Every C++ program must have it
4. **cout** — Used to print output
5. **cin** — Used to take input
6. **return 0** — Tells OS program ended successfully

---

## 📌 Data Types in C++

| Data Type | Size | Example |
|-----------|------|---------|
| `int` | 4 bytes | 10, -5, 100 |
| `float` | 4 bytes | 3.14, 9.5 |
| `double` | 8 bytes | 3.14159265 |
| `char` | 1 byte | 'A', 'z' |
| `bool` | 1 byte | true, false |
| `void` | 0 bytes | No value |

---

## 📌 Variables and Constants

```cpp
// Variable — value can change
int age = 18;
float price = 99.5;
char grade = 'A';

// Constant — value cannot change
const float PI = 3.14;
const int MAX = 100;
```

> **Variable:** A named memory location to store data that can change.
> **Constant:** A named memory location to store data that CANNOT change.

---

## 📌 Keywords in C++

> **Keywords = Reserved words with special meaning. Cannot be used as variable names.**

Important keywords:
`int`, `float`, `char`, `bool`, `void`, `if`, `else`, `for`, `while`, `do`, `break`, `continue`, `return`, `class`, `public`, `private`, `new`, `delete`, `const`

---

## 📌 Operators in C++

### Arithmetic Operators:
| Operator | Meaning | Example |
|----------|---------|---------|
| `+` | Addition | 5+3 = 8 |
| `-` | Subtraction | 5-3 = 2 |
| `*` | Multiplication | 5*3 = 15 |
| `/` | Division | 6/2 = 3 |
| `%` | Modulus (remainder) | 7%3 = 1 |

### Relational Operators:
`==`, `!=`, `>`, `<`, `>=`, `<=`

### Logical Operators:
| Operator | Meaning |
|----------|---------|
| `&&` | AND |
| `||` | OR |
| `!` | NOT |

### Increment/Decrement:
- `++a` — Pre-increment (increment first, then use)
- `a++` — Post-increment (use first, then increment)
- `--a` — Pre-decrement
- `a--` — Post-decrement

---

## 📌 Loops

### for Loop
```cpp
// Print 1 to 5
for (int i = 1; i <= 5; i++) {
    cout << i << " ";
}
// Output: 1 2 3 4 5
```
**Syntax:** `for (initialization; condition; increment)`
- Use when you **know** how many times to loop

### while Loop
```cpp
int i = 1;
while (i <= 5) {
    cout << i << " ";
    i++;
}
// Output: 1 2 3 4 5
```
- Use when you **don't know** how many times to loop
- Checks condition BEFORE executing

### do-while Loop
```cpp
int i = 1;
do {
    cout << i << " ";
    i++;
} while (i <= 5);
```
- Executes body **at least once** even if condition is false
- Checks condition AFTER executing

| Loop | Condition Check | Minimum Executions |
|------|----------------|--------------------|
| `for` | Before | 0 |
| `while` | Before | 0 |
| `do-while` | After | 1 |

---

## 📌 Arrays

> **Array = A collection of elements of the same data type stored in continuous memory**

```cpp
// Declaration
int marks[5];

// Declaration with initialization
int marks[5] = {85, 90, 75, 88, 92};

// Accessing elements (index starts from 0)
cout << marks[0];   // prints 85
cout << marks[2];   // prints 75

// Traversing array with loop
for (int i = 0; i < 5; i++) {
    cout << marks[i] << " ";
}
```

**Key Points:**
- Index starts from **0** (not 1)
- `marks[5]` means 5 elements: index 0,1,2,3,4
- All elements must be of **same data type**

---

## ⭐ 5-Mark Answer: Explain for loop and while loop with examples

**Loops** are used in programming to execute a block of code repeatedly. C++ has three types of loops.

**for Loop:**
The for loop is used when the number of iterations is known in advance. It has three parts: initialization, condition, and increment/decrement.

```cpp
// Example: Print table of 5
for (int i = 1; i <= 10; i++) {
    cout << 5 * i << endl;
}
```
Execution: i starts at 1, prints 5×1=5; i becomes 2, prints 5×2=10; continues till i=10.

**while Loop:**
The while loop is used when the number of iterations is not known. It checks the condition first; if true, it executes the body.

```cpp
// Example: Input until user enters 0
int n;
cin >> n;
while (n != 0) {
    cout << n;
    cin >> n;
}
```

**Key Difference:** The for loop checks condition before execution (entry-controlled). The while loop also checks before execution but is preferred when iterations are unknown. The do-while loop checks condition after execution, guaranteeing at least one execution.

---

---

# 4. Data Structures

## 🔑 What is a Data Structure?
- **Data Structure = A way to organize and store data in computer memory**
- Makes data easier to access and work with

## 📌 Linear vs Non-Linear

| Linear | Non-Linear |
|--------|------------|
| Data in sequence | Data in hierarchy |
| Array, Stack, Queue, Linked List | Tree, Graph |
| Simple to implement | Complex |
| Single level | Multi-level |

---

## 📌 STACK (LIFO)

> **Stack = A data structure where insertion and deletion happen from the SAME end (TOP)**
> **LIFO = Last In, First Out** — Jo last me aaya, wo pehle nikalta hai

**Real life example:** Stack of plates — last plate placed is first taken

### Operations:
| Operation | Description |
|-----------|-------------|
| `PUSH` | Insert element at TOP |
| `POP` | Delete element from TOP |
| `PEEK/TOP` | View top element without deleting |
| `isEmpty` | Check if stack is empty |
| `isFull` | Check if stack is full |

### Stack example:
```
Push: 10 → Stack: [10]
Push: 20 → Stack: [10, 20]
Push: 30 → Stack: [10, 20, 30]  ← TOP
Pop       → Returns 30, Stack: [10, 20]
Pop       → Returns 20, Stack: [10]
```

### Stack using Array (C++):
```cpp
int stack[100];
int top = -1;           // -1 means empty

// PUSH
stack[++top] = 10;      // top becomes 0, insert 10

// POP
int val = stack[top--]; // take value, then decrease top
```

> **Overflow** = Pushing when stack is full
> **Underflow** = Popping when stack is empty

---

## 📌 QUEUE (FIFO)

> **Queue = A data structure where insertion happens at REAR and deletion at FRONT**
> **FIFO = First In, First Out** — Jo pehle aaya, wo pehle nikalta hai

**Real life example:** Queue at a ticket counter

### Operations:
| Operation | Description |
|-----------|-------------|
| `ENQUEUE` | Insert at REAR |
| `DEQUEUE` | Delete from FRONT |
| `PEEK` | View front element |

### Queue example:
```
Enqueue 10 → Queue: [10]         FRONT=10, REAR=10
Enqueue 20 → Queue: [10, 20]     FRONT=10, REAR=20
Enqueue 30 → Queue: [10, 20, 30] FRONT=10, REAR=30
Dequeue    → Returns 10, Queue: [20, 30]
```

---

## 📌 Stack vs Queue

| | Stack | Queue |
|-|-------|-------|
| Principle | LIFO | FIFO |
| Insertion end | TOP | REAR |
| Deletion end | TOP | FRONT |
| Example | Undo in editor | Printer queue |

---

## 📌 Linked List

> **Linked List = A series of nodes where each node stores DATA and address of NEXT node**

```
[Data|Next] → [Data|Next] → [Data|Next] → NULL
   10            20            30
```

**Each node has two parts:**
1. **Data** — stores the value
2. **Link/Next** — stores address of next node

**Types:**
- **Singly Linked List** — Each node points to next
- **Doubly Linked List** — Each node points to next AND previous
- **Circular Linked List** — Last node points back to first

**Advantages over Array:**
- Dynamic size (can grow/shrink at runtime)
- Easy insertion and deletion

**Disadvantage:**
- No direct access (must traverse from start)
- Extra memory for storing address

---

## ⭐ 5-Mark Answer: Explain Stack with PUSH and POP operations

**Stack** is a linear data structure that follows the **LIFO (Last In, First Out)** principle. This means the element inserted last will be removed first. Think of it like a stack of plates — you always take from the top.

**Basic Operations:**

**PUSH Operation** (Insertion):
- Insert an element at the TOP of the stack
- Before pushing, check for **overflow** (stack full condition)
- Steps: (1) Check if top == MAX-1 (overflow). (2) Increment top by 1. (3) Insert element at stack[top].

```cpp
void push(int val) {
    if (top == MAX - 1)
        cout << "Stack Overflow!";
    else
        stack[++top] = val;
}
```

**POP Operation** (Deletion):
- Remove element from TOP of stack
- Before popping, check for **underflow** (stack empty condition)
- Steps: (1) Check if top == -1 (underflow). (2) Store stack[top]. (3) Decrement top.

```cpp
int pop() {
    if (top == -1)
        cout << "Stack Underflow!";
    else
        return stack[top--];
}
```

**Example Trace:**
- Push(10) → [10], top=0
- Push(20) → [10,20], top=1
- Push(30) → [10,20,30], top=2
- Pop() → returns 30, top=1
- Pop() → returns 20, top=0

**Applications of Stack:** Expression evaluation, undo operations in editors, function call management (recursion).

---

---

# 5. Boolean Algebra

## 🔑 What is Boolean Algebra?
- **Boolean Algebra = A branch of mathematics dealing with TRUE (1) and FALSE (0)**
- Used in digital circuits and computers
- Developed by **George Boole**

---

## 📌 Basic Logic Gates

### AND Gate
- **Output = 1 only when ALL inputs are 1**
- Symbol: A · B or A AND B

**Truth Table — AND Gate:**
| A | B | A · B (Output) |
|---|---|----------------|
| 0 | 0 | **0** |
| 0 | 1 | **0** |
| 1 | 0 | **0** |
| 1 | 1 | **1** |

### OR Gate
- **Output = 1 when ANY input is 1**
- Symbol: A + B or A OR B

**Truth Table — OR Gate:**
| A | B | A + B (Output) |
|---|---|----------------|
| 0 | 0 | **0** |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **1** |

### NOT Gate (Inverter)
- **Output = Opposite of input**
- Symbol: Ā or NOT A

**Truth Table — NOT Gate:**
| A | Ā (Output) |
|---|------------|
| 0 | **1** |
| 1 | **0** |

---

## 📌 Basic Laws of Boolean Algebra

### Identity Laws:
- A + 0 = A
- A · 1 = A

### Null/Dominance Laws:
- A + 1 = 1
- A · 0 = 0

### Idempotent Laws:
- A + A = A
- A · A = A

### Complement Laws:
- A + Ā = 1
- A · Ā = 0

### Double Negation Law:
- Ā̄ = A (NOT NOT A = A)

### Commutative Laws:
- A + B = B + A
- A · B = B · A

### Associative Laws:
- A + (B + C) = (A + B) + C
- A · (B · C) = (A · B) · C

### Distributive Laws:
- A · (B + C) = A·B + A·C
- A + (B · C) = (A+B) · (A+C)

### De Morgan's Theorems: ⭐ (Very Important!)
- **(A + B)' = A' · B'** — NOT(A OR B) = (NOT A) AND (NOT B)
- **(A · B)' = A' + B'** — NOT(A AND B) = (NOT A) OR (NOT B)

---

## 📌 NAND and NOR Gates

### NAND Gate = NOT + AND
- **Output = 0 only when ALL inputs are 1**
- Called **Universal Gate** (can create any other gate)

**Truth Table — NAND:**
| A | B | Output |
|---|---|--------|
| 0 | 0 | **1** |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **0** |

### NOR Gate = NOT + OR
- **Output = 1 only when ALL inputs are 0**
- Also called **Universal Gate**

**Truth Table — NOR:**
| A | B | Output |
|---|---|--------|
| 0 | 0 | **1** |
| 0 | 1 | **0** |
| 1 | 0 | **0** |
| 1 | 1 | **0** |

> **NAND and NOR are called Universal Gates because any other gate can be built using only NAND (or only NOR) gates.**

---

## ⭐ 5-Mark Answer: Explain Boolean Algebra with gates and truth tables

**Boolean Algebra** is a system of algebra that works with binary values — **1 (TRUE)** and **0 (FALSE)**. It was developed by mathematician **George Boole** and forms the mathematical foundation of digital computers.

**Three Basic Operations:**

1. **AND Operation (·):** Output is 1 only when all inputs are 1. Used in multiplication logic.
   - 0·0=0, 0·1=0, 1·0=0, 1·1=**1**

2. **OR Operation (+):** Output is 1 when at least one input is 1.
   - 0+0=0, 0+1=**1**, 1+0=**1**, 1+1=**1**

3. **NOT Operation ('):** Inverts the input.
   - NOT 0 = **1**, NOT 1 = **0**

**Important Laws:**
- **Identity Law:** A+0=A, A·1=A
- **Complement Law:** A+A'=1, A·A'=0
- **De Morgan's Theorem:** (A+B)' = A'·B' and (A·B)' = A'+B'

**De Morgan's Theorem** is very important because it allows us to convert between AND/OR operations with negation.

**Universal Gates:** NAND and NOR are called Universal Gates because any Boolean function can be implemented using only NAND gates or only NOR gates. This reduces manufacturing cost of circuits.

---

---

# 6. MCQ Quick Revision

## SQL MCQs
- DDL stands for → **Data Definition Language**
- DML stands for → **Data Manipulation Language**
- SELECT command is part of → **DML**
- `DROP TABLE` is part of → **DDL**
- `CHAR` vs `VARCHAR` → CHAR is **fixed** length, VARCHAR is **variable** length
- `DELETE` without WHERE → deletes **all rows** but keeps table
- `TRUNCATE` vs `DELETE` → TRUNCATE is **DDL**, DELETE is **DML**
- `LIKE 'A%'` means → starts with **A**
- `LIKE '%s'` means → ends with **s**
- Primary key → **uniquely identifies** each row

## Networking MCQs
- Full form of LAN → **Local Area Network**
- Full form of WAN → **Wide Area Network**
- Internet is an example of → **WAN**
- OSI model has → **7 layers**
- Topmost layer of OSI → **Application Layer**
- Bottommost layer of OSI → **Physical Layer**
- HTTP is used for → **Web browsing**
- FTP is used for → **File Transfer**
- SMTP is used for → **Sending emails**
- Fastest transmission media → **Optical Fiber**
- Star topology central device → **Hub or Switch**
- Universal gate → **NAND and NOR**

## C++ MCQs
- `cin` is used for → **input**
- `cout` is used for → **output**
- Array index starts from → **0**
- `%` operator gives → **remainder**
- `do-while` executes minimum → **1 time**
- `const` keyword is used for → **constants**
- `bool` data type stores → **true or false**
- `++a` is called → **pre-increment**

## Data Structure MCQs
- Stack follows → **LIFO**
- Queue follows → **FIFO**
- Stack insertion operation → **PUSH**
- Stack deletion operation → **POP**
- Queue insertion → **ENQUEUE** at **REAR**
- Queue deletion → **DEQUEUE** from **FRONT**
- Stack overflow means → **pushing to a full stack**
- Stack underflow means → **popping from empty stack**
- Linked list node contains → **data + address of next node**
- Array vs Linked List → Array has **fixed** size, Linked list has **dynamic** size

## Boolean MCQs
- AND gate output is 1 when → **all inputs are 1**
- OR gate output is 0 when → **all inputs are 0**
- NOT gate is also called → **Inverter**
- NAND = NOT + → **AND**
- NOR = NOT + → **OR**
- Universal gate → **NAND / NOR**
- A + A' = → **1**
- A · A' = → **0**
- (A+B)' = → **A'·B'** (De Morgan's)
- (A·B)' = → **A'+B'** (De Morgan's)

---

---

## 📝 Important 2-Mark Definitions (Quick List)

1. **SQL** = Structured Query Language — used to manage relational databases
2. **DDL** = Commands that define database structure (CREATE, DROP, ALTER)
3. **DML** = Commands that manipulate data (INSERT, UPDATE, DELETE, SELECT)
4. **Primary Key** = Column that uniquely identifies each row in a table
5. **LAN** = Network covering small area like a building or school
6. **Protocol** = Set of rules governing communication between computers
7. **Topology** = Physical layout/arrangement of computers in a network
8. **OSI Model** = 7-layer model describing data transmission across a network
9. **Stack** = Linear data structure following LIFO principle
10. **Queue** = Linear data structure following FIFO principle
11. **Linked List** = Data structure where nodes are connected using pointers
12. **Boolean Algebra** = Algebra using binary values (0 and 1)
13. **Universal Gate** = Gate using which all other gates can be made (NAND/NOR)
14. **Variable** = Named memory location that can store changing values
15. **Constant** = Named memory location whose value cannot be changed
16. **Array** = Collection of same-type elements stored in continuous memory
17. **Keyword** = Reserved words in C++ with predefined meaning
18. **Loop** = Program construct used to execute code repeatedly

---

## ✅ Last Minute Exam Tips

- **SQL**: Remember DDL vs DML difference — very commonly asked
- **SELECT with WHERE**: Practice writing queries with conditions
- **OSI Model**: Remember all 7 layers with trick "**A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing"
- **Stack**: Always write LIFO, PUSH/POP, overflow/underflow
- **Queue**: Always write FIFO, ENQUEUE at REAR, DEQUEUE from FRONT
- **Boolean**: Write truth tables completely — all 4 rows
- **De Morgan's Theorem**: Very important — memorize both formulas
- **C++ program**: Always include `#include<iostream>` and `using namespace std;`

---

> 📌 **Best of luck for your exam! You've got this! 🎯**
>
> *Made for Bihar Board Class 12 Computer Science Exam Revision*
