# ⚠️ Fix "Unchecked or Unsafe Operations" Warning in IntelliJ IDEA

## 🚨 Warning Meaning

The warning:

```
java: Some input files use unchecked or unsafe operations.
java: Recompile with -Xlint:unchecked for details.
```

indicates that your code contains **unchecked or unsafe operations**, often due to:

- **Raw types in generics** (e.g., `List list = new ArrayList();` instead of `List<String> list = new ArrayList<>();`)
- **Unsafe type casting** (e.g., `(List<String>) obj` without checking)
- **Mixing generic and non-generic code** (e.g., calling methods with `Object` instead of specific types)

---

## 🔎 How to Check Details in IntelliJ IDEA

To **see the exact lines** causing the issue, enable `-Xlint:unchecked` in IntelliJ.

### ✅ Method 1: Add Compiler Option (`-Xlint:unchecked`)
1. **Go to** `File → Settings → Build, Execution, Deployment → Compiler → Java Compiler`
2. In **"Additional command line parameters"**, add:
   ```
   -Xlint:unchecked
   ```
3. Click **Apply** and **OK**.
4. **Rebuild the project** (`Build → Rebuild Project`).
5. The warnings will now show **detailed messages with line numbers**.

---

### ✅ Method 2: Enable Compiler Warnings
1. **Go to** `File → Settings → Editor → Inspections`
2. In the search bar, type `"unchecked"`.
3. Enable:
   - **"Unchecked generics usage"**
   - **"Unchecked assignment"**
   - **"Raw use of parameterized class"**
4. Click **Apply** and **OK**.
5. **Recompile the project**, and IntelliJ will highlight the warnings in the editor.

---

## 🛠️ How to Fix the Warning

After enabling `-Xlint:unchecked`, IntelliJ will **point out the problematic code**. Here are **common fixes**:

### 🔹 **1. Fix Raw Types in Generics**
❌ **Before (Unsafe)**
```java
List list = new ArrayList(); // Raw type, no generics
list.add("Hello");
String value = (String) list.get(0);
```
✔ **After (Fixed)**
```java
List<String> list = new ArrayList<>();
list.add("Hello");
String value = list.get(0); // No cast needed
```

---

### 🔹 **2. Fix Unchecked Type Casts**
❌ **Before (Unsafe Cast)**
```java
Object obj = "Hello";
List<String> list = (List<String>) obj; // Unsafe cast
```
✔ **After (Fixed)**
```java
Object obj = "Hello";
if (obj instanceof List<?>) {
    List<?> tempList = (List<?>) obj; // Safe cast
}
```

---

### 🔹 **3. Fix `Map` Without Generic Types**
❌ **Before (Unsafe)**
```java
Map map = new HashMap();
map.put(1, "One");
String value = (String) map.get(1);
```
✔ **After (Fixed)**
```java
Map<Integer, String> map = new HashMap<>();
map.put(1, "One");
String value = map.get(1);
```

---

## 📌 Next Steps
1. **Enable `-Xlint:unchecked` in IntelliJ** (Method 1).
2. **Rebuild the project** (`Build → Rebuild Project`).
3. **Check the warnings IntelliJ highlights** and fix them using generics.
4. **Recompile and verify that warnings are gone.**

---

### 🎉 **Congratulations! You Have Fixed the Warning! 🚀**
