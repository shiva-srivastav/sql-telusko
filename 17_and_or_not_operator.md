

# **SQL: AND, OR, NOT Operators**

### **Theory**
- **AND Operator**: Combines two or more conditions and returns rows only when all conditions are true.
- **OR Operator**: Combines two or more conditions and returns rows when any one of the conditions is true.
- **NOT Operator**: Used to negate a condition; it returns rows where the condition is false.



### **Commutative, Associative, and Distributive Properties**

#### **Commutative Property**
- The **commutative property** means that the order of the conditions does not affect the result.
- Applicable for both **AND** and **OR** operators.

**Example (Commutative):**
```sql
SELECT * FROM studentinfo WHERE age=18 OR city='Pune';
SELECT * FROM studentinfo WHERE city='Pune' OR age=18;
```
**Result:** Both queries produce the same output because the OR operator is commutative.

#### **Associative Property**
- The **associative property** means that the grouping of conditions does not affect the result.
- Applicable for both **AND** and **OR** operators.

**Example (Associative):**
```sql
SELECT * FROM studentinfo WHERE (age=18 OR city='Pune') OR city='Mumbai';
SELECT * FROM studentinfo WHERE age=18 OR (city='Pune' OR city='Mumbai');
```
**Result:** Both queries produce the same output because the OR operator is associative.

#### **Distributive Property**
- The **distributive property** shows how **AND** and **OR** work together.
- A condition with **AND** and **OR** can be distributed as:
  - `(A AND (B OR C))` is equivalent to `((A AND B) OR (A AND C))`.
  - `(A OR (B AND C))` is equivalent to `((A OR B) AND (A OR C))`.

**Example (Distributive):**
```sql
SELECT * FROM studentinfo WHERE age=18 AND (city='Pune' OR city='Mumbai');
SELECT * FROM studentinfo WHERE (age=18 AND city='Pune') OR (age=18 AND city='Mumbai');
```
**Result:** Both queries produce the same output because the AND and OR operators distribute correctly.

---

### **Examples and Outputs**

#### **1. Using OR Operator**
**Query:**
```sql
SELECT * FROM studentinfo WHERE age=18 OR age=20;
```
**Output:**
| S.ID | Name   | Age | City       |
|------|--------|-----|------------|
| 1    | John   | 18  | Bengaluru  |
| 3    | Rahul  | 20  | Pune       |
| 5    | Neha   | 18  | Mumbai     |

**Explanation:** This query retrieves rows where the age is either 18 or 20.

---

#### **2. Using AND Operator**
**Query:**
```sql
SELECT * FROM studentinfo WHERE age=18 AND city='Pune';
```
**Output:**
| S.ID | Name   | Age | City       |
|------|--------|-----|------------|
| 3    | Rahul  | 18  | Pune       |

**Explanation:** This query retrieves rows where both conditions (age is 18 and city is Pune) are true.

---

#### **3. Combining AND and OR Operators**
**Query:**
```sql
SELECT * FROM studentinfo WHERE city='Bengaluru' OR city='London' AND age=19;
```
**Output:**
| S.ID | Name   | Age | City       |
|------|--------|-----|------------|
| 2    | Rohit  | 19  | London     |
| 4    | Priya  | 22  | Bengaluru  |

**Explanation:** The query retrieves rows where the city is Bengaluru or where both city is London and age is 19.

---

#### **4. Using NOT Operator**
**Query:**
```sql
SELECT * FROM studentinfo WHERE NOT (city='Bengaluru' OR city='London') AND age=19;
```
**Output:**
| S.ID | Name   | Age | City       |
|------|--------|-----|------------|
| 6    | Akash  | 19  | Pune       |

**Explanation:** This query retrieves rows where the city is neither Bengaluru nor London, and the age is 19.

---

### **Summary**
- Use **AND** to filter rows meeting all conditions.
- Use **OR** to filter rows meeting any of the conditions.
- Use **NOT** to exclude rows matching a condition.
- **Commutative Property**: The order of conditions does not matter for **AND** and **OR**.
- **Associative Property**: The grouping of conditions does not matter for **AND** and **OR**.
- **Distributive Property**: Conditions with **AND** and **OR** can be distributed equivalently for clarity and efficiency.

---

