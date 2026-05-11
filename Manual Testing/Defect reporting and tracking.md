# Defects in Software Testing

## 📌 What is a Defect?

Any **mismatch between expected and actual functionality** in an application is called a:

👉 **Defect / Bug / Issue**

---

## 🛠️ Defect Reporting Tools

Common tools used to report and track defects:

- ClearQuest  
- DevTrack  
- Jira  
- Quality Center (ALM)  
- Bugzilla  

---

## ⚠️ Severity vs Priority

### ✅ Severity
- Refers to the **impact of the bug on the application**
- Defined by the **tester**
- Measures how serious the defect is in the system

**Levels:**
- 🔴 Blocker → Application cannot proceed (system crash, login failure)
- 🔴 Critical → Major functionality broken, no workaround
- 🟠 Major → Important feature not working properly
- 🟢 Minor → Small issue (UI issues, minor bugs)

---

### ✅ Priority
- Refers to how quickly a defect should be fixed
- Defined by the **business/client/manager**
- Based on **business impact**

**Levels:**
- High (P1) → Fix immediately  
- Medium (P2) → Fix soon  
- Low (P3) → Fix later  

---

## 🔁 Bug Life Cycle

The **Bug Life Cycle** describes the stages a defect goes through from detection to closure.

### 🧾 Initial Checks:
1. ✅ **Is it a valid defect?**  
   - Verify if the issue is actually a bug  

2. ✅ **Is it in scope?**  
   - Check whether it belongs to the current project/module  

3. ✅ **Is it already raised?**  
   - Avoid duplicate defects  

---

### 🔄 Typical Bug Status Flow

1. **New** → Bug is reported  
2. **Assigned** → Assigned to developer  
3. **Open** → Developer starts fixing  
4. **Fixed** → Issue resolved by developer  
5. **Retest** → Tester verifies fix  
6. **Closed** → Bug is successfully fixed  
7. **Reopen** → If issue still exists  

---

## 🎯 Summary

- Defect = **Mismatch in functionality**
- Severity = **Technical impact**
- Priority = **Business urgency**
- Bug Life Cycle = **Steps from detection to closure**

---
```
