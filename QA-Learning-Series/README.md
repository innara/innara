# 🧪 QA Learning Series: A Practical Guide to Testing Excellence

<div align="center">

**Practical insights from 3+ years of Software Quality Assurance work** 

*Master the fundamentals of testing, discover common bugs, and level up your QA skills*

</div>

---

## 📌 Table of Contents

1. [Introduction](#introduction)
2. [Purpose of This Repository](#purpose-of-this-repository)
3. [Top 10 Test Cases for Login Functionality](#top-10-test-cases-for-login-functionality)
4. [Common Bugs in Fintech Applications](#common-bugs-in-fintech-applications)
5. [About Me](#about-me)
6. [Connect With Me](#connect-with-me)

---

## 🎯 Introduction

Welcome to the **QA Learning Series**! 

As a QA engineer with 3+ years of hands-on experience in web and mobile testing, I've learned that **great testing is about understanding patterns**—both the patterns that make software reliable and the patterns that reveal bugs.

This repository is my attempt to share practical, real-world testing knowledge that goes beyond theory. Whether you're starting your QA journey or looking to sharpen your skills, you'll find:

- ✅ Detailed test scenarios for critical features
- ✅ Real fintech bugs and how to catch them
- ✅ Best practices from years of testing experience
- ✅ A beginner-friendly approach to complex problems

---

## 🚀 Purpose of This Repository

This isn't a textbook. It's a **practical playbook** for:

- **QA Beginners** 👨‍🎓 - Learn how to write effective test cases with real examples
- **Testing Enthusiasts** 🔍 - Understand common vulnerabilities in fintech applications
- **Hiring Managers & Recruiters** 💼 - See my testing approach and attention to detail
- **Career-Switchers** 🎯 - Get a foundation in modern QA practices

### What You'll Learn:
- How to design comprehensive test cases
- What bugs to look for in financial applications
- Why certain tests matter more than others
- The difference between finding bugs and understanding systems

---

## 📋 Top 10 Test Cases for Login Functionality

Login is the **first line of defense** in any application. Here are 10 critical test cases that every QA engineer should master:

### **Test Case 1: Valid Credentials - Successful Login**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_001 |
| **Objective** | Verify that a user can successfully log in with valid credentials |
| **Preconditions** | User account exists in the system; user is on the login page |
| **Steps** | 1. Enter valid email/username<br>2. Enter valid password<br>3. Click "Login" button |
| **Expected Result** | User is redirected to the dashboard; session is created; user role displays correctly |
| **Type** | Positive Test |

---

### **Test Case 2: Invalid Password - Login Fails**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_002 |
| **Objective** | Verify that login fails with an incorrect password |
| **Preconditions** | Valid user account exists; user is on the login page |
| **Steps** | 1. Enter valid email/username<br>2. Enter incorrect password<br>3. Click "Login" button |
| **Expected Result** | Error message appears: "Invalid password"<br>User remains on login page<br>Session is NOT created |
| **Type** | Negative Test |

---

### **Test Case 3: Non-existent User - Login Fails**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_003 |
| **Objective** | Verify that login fails for a non-existent user account |
| **Preconditions** | User account does NOT exist; user is on the login page |
| **Steps** | 1. Enter non-existent email/username<br>2. Enter any password<br>3. Click "Login" button |
| **Expected Result** | Error message appears: "User not found" or "Invalid credentials"<br>User remains on login page<br>No session created |
| **Type** | Negative Test |

---

### **Test Case 4: Empty Username/Email Field**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_004 |
| **Objective** | Verify that the form validates empty username field |
| **Preconditions** | User is on the login page |
| **Steps** | 1. Leave email/username field empty<br>2. Enter valid password<br>3. Click "Login" button |
| **Expected Result** | Inline validation error: "Email/Username is required"<br>Login button is disabled or form prevents submission |
| **Type** | Validation Test |

---

### **Test Case 5: Empty Password Field**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_005 |
| **Objective** | Verify that the form validates empty password field |
| **Preconditions** | User is on the login page |
| **Steps** | 1. Enter valid email/username<br>2. Leave password field empty<br>3. Click "Login" button |
| **Expected Result** | Inline validation error: "Password is required"<br>Login button is disabled or form prevents submission |
| **Type** | Validation Test |

---

### **Test Case 6: SQL Injection Attack - Username Field**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_006 |
| **Objective** | Verify that the login form is protected against SQL injection attacks |
| **Preconditions** | User is on the login page |
| **Steps** | 1. Enter SQL injection payload in username: `' OR '1'='1`<br>2. Enter any password<br>3. Click "Login" button |
| **Expected Result** | Login fails with error message<br>Payload is treated as literal text, not SQL<br>No unauthorized access granted |
| **Type** | Security Test |

---

### **Test Case 7: Account Locked After Failed Attempts**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_007 |
| **Objective** | Verify that account locks after N failed login attempts (e.g., 5) |
| **Preconditions** | Valid user account exists; user is on the login page |
| **Steps** | 1. Enter correct username<br>2. Enter incorrect password 5 times<br>3. Attempt login on 6th attempt |
| **Expected Result** | Account is locked after 5 failed attempts<br>Error message: "Account locked due to multiple failed attempts"<br>User cannot log in even with correct password |
| **Type** | Security Test |

---

### **Test Case 8: Password Reset Link - Functionality**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_008 |
| **Objective** | Verify that the "Forgot Password" link works correctly |
| **Preconditions** | User is on the login page; valid email account exists |
| **Steps** | 1. Click "Forgot Password" link<br>2. Enter registered email<br>3. Verify email received<br>4. Click reset link in email<br>5. Set new password |
| **Expected Result** | Email with reset link is sent within 2 minutes<br>Reset link is valid for 24 hours<br>User can set new password<br>User can log in with new password |
| **Type** | Functional Test |

---

### **Test Case 9: Session Timeout - Auto Logout**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_009 |
| **Objective** | Verify that user is logged out after inactivity timeout |
| **Preconditions** | User is logged in; session timeout is set to 15 minutes |
| **Steps** | 1. Log in successfully<br>2. Leave the application idle for 15+ minutes<br>3. Try to perform an action |
| **Expected Result** | User is automatically logged out<br>User is redirected to login page<br>Warning message may appear before logout |
| **Type** | Security Test |

---

### **Test Case 10: Remember Me Functionality**
| Field | Value |
|-------|-------|
| **Test Case ID** | TC_LOGIN_010 |
| **Objective** | Verify that "Remember Me" checkbox persists login credentials securely |
| **Preconditions** | User is on the login page; browser cookies are enabled |
| **Steps** | 1. Enter valid credentials<br>2. Check "Remember Me" checkbox<br>3. Click "Login" button<br>4. Log out<br>5. Return to login page |
| **Expected Result** | Email/username is pre-filled on return visit<br>Password is NOT displayed (security best practice)<br>User can log in with one click |
| **Type** | Functional Test |

---

## 🐛 Common Bugs in Fintech Applications

Working in fintech QA has taught me that **one bug can cost money—literally**. Here are the bugs I've caught most frequently:

### **Bug #1: Transaction Amount Validation Bypass**

**Severity:** 🔴 **CRITICAL**

**Description:**
User can enter negative amounts or amounts exceeding daily limits through client-side validation bypass.

**How to Catch It:**
- Test with invalid characters: `-500`, `999999999`
- Use browser DevTools to modify the validation script
- Test via API directly (Postman) bypassing UI validation

**Real Impact:**
- Unauthorized transactions
- Potential financial loss
- Compliance violations

**Prevention:**
```
✅ Always validate on the server-side
✅ Use strong data type checks (e.g., decimal with 2 places max)
✅ Enforce database constraints
```

---

### **Bug #2: Decimal Precision Issues**

**Severity:** 🟠 **HIGH**

**Description:**
Rounding errors accumulate when calculating transaction fees or currency conversions (e.g., `0.1 + 0.2 = 0.30000000000000004`)

**How to Catch It:**
- Test with amounts ending in .01, .99
- Create 1000+ transactions and verify total balance
- Test currency conversions with multiple decimal places

**Real Impact:**
- Money disappears or appears from nowhere
- Audit failures
- Customer complaints

**Prevention:**
```
✅ Use fixed-point arithmetic for financial calculations
✅ Store amounts as integers (e.g., cents, not dollars)
✅ Never use floating-point for money
```

---

### **Bug #3: Session Hijacking - No HTTPS Enforcement**

**Severity:** 🔴 **CRITICAL**

**Description:**
Login credentials transmitted over HTTP instead of HTTPS; session cookies not marked as Secure/HttpOnly.

**How to Catch It:**
- Test login page with browser Dev Tools (Network tab)
- Check request/response headers for `Secure` and `HttpOnly` flags
- Use tools like Wireshark or Postman to intercept traffic

**Real Impact:**
- Credentials stolen via man-in-the-middle attacks
- Unauthorized account access
- Massive security breach

**Prevention:**
```
✅ Enforce HTTPS for all endpoints
✅ Set Secure flag on session cookies
✅ Set HttpOnly flag to prevent JavaScript access
✅ Use HSTS headers
```

---

### **Bug #4: Race Condition - Double Charging**

**Severity:** 🔴 **CRITICAL**

**Description:**
Rapid successive clicks on "Pay" button charges the user multiple times due to lack of idempotency.

**How to Catch It:**
- Rapid-click the payment button
- Use browser DevTools to throttle network and click multiple times
- Create automated test with parallel requests

**Real Impact:**
- Customer double-charged
- Chargeback disputes
- Customer dissatisfaction and loss of trust

**Prevention:**
```
✅ Implement idempotency keys for transactions
✅ Disable button after first click
✅ Add server-side duplicate detection
✅ Use database constraints to prevent duplicates
```

---

### **Bug #5: Insufficient Permission Checks**

**Severity:** 🔴 **CRITICAL**

**Description:**
User can access/modify other users' account data by changing URL parameters or user IDs in API calls.

**How to Catch It:**
- Log in as User A
- Modify URL from `/accounts/123` to `/accounts/456`
- Try accessing other user's transaction history via API
- Use Postman to directly call API with different user IDs

**Real Impact:**
- Complete privacy violation
- Regulatory fines (GDPR, PCI-DSS)
- Loss of customer trust
- Legal liability

**Prevention:**
```
✅ Verify user ownership of resources
✅ Use role-based access control (RBAC)
✅ Implement server-side authorization checks
✅ Log all access attempts
```

---

### **Bug #6: Incorrect Timezone Handling**

**Severity:** 🟠 **HIGH**

**Description:**
Transactions show incorrect timestamps; daily/monthly reports include wrong data due to timezone mishandling.

**How to Catch It:**
- Change device timezone before transaction
- Check transaction timestamp in app vs. database
- Test user in different timezones

**Real Impact:**
- Reconciliation issues
- Wrong reporting for compliance
- Audit failures

**Prevention:**
```
✅ Store all times in UTC
✅ Convert to user timezone only for display
✅ Include timezone info in API responses
✅ Test across multiple timezones
```

---

### **Bug #7: No Rate Limiting - Brute Force Attack**

**Severity:** 🟠 **HIGH**

**Description:**
API endpoints have no rate limiting; attacker can brute-force login credentials or enumerate user accounts.

**How to Catch It:**
- Use automation tool to send 1000 requests in seconds
- Try logging in 100 times with different passwords
- Use Postman collection runner to hammer API

**Real Impact:**
- Account takeovers
- Denial of service
- Privacy violations (user enumeration)

**Prevention:**
```
✅ Implement rate limiting per IP/user
✅ Add CAPTCHA after N failed attempts
✅ Lock accounts after failed attempts
✅ Monitor API for suspicious patterns
```

---

### **Bug #8: Sensitive Data in Logs**

**Severity:** 🟠 **HIGH**

**Description:**
Passwords, credit card numbers, or API keys logged in plain text in application logs or error messages.

**How to Catch It:**
- Check application logs for sensitive data
- Look at error messages displayed to users
- Check browser console for sensitive info in API responses
- Review network requests in DevTools

**Real Impact:**
- Compliance violations
- Data breach
- Potential credit card fraud

**Prevention:**
```
✅ Never log passwords or PII
✅ Hash/mask sensitive data in logs
✅ Use structured logging with security review
✅ Implement log retention policies
```

---

### **Bug #9: Weak Password Requirements**

**Severity:** 🟠 **HIGH**

**Description:**
Application allows weak passwords like `1234` or `password`; no complexity requirements.

**How to Catch It:**
- Try creating account with password: `1234`
- Try password: `123456`
- Try password: `password`
- Check password policy documentation

**Real Impact:**
- Easy account takeovers
- Brute-force attacks succeed quickly
- Customer accounts compromised

**Prevention:**
```
✅ Minimum 12 characters
✅ Require mix of uppercase, lowercase, numbers, special chars
✅ Check against common password list
✅ Educate users on password security
```

---

### **Bug #10: Missing CSRF Protection**

**Severity:** 🔴 **CRITICAL**

**Description:**
Cross-Site Request Forgery attack possible; attacker can perform actions on behalf of authenticated user.

**How to Catch It:**
- Check for CSRF tokens in forms
- Try submitting forms from different websites
- Verify token validation on server

**Real Impact:**
- Unauthorized transactions
- User data modified
- Account compromise

**Prevention:**
```
✅ Implement CSRF tokens on all state-changing requests
✅ Validate tokens on server
✅ Use SameSite cookie flag
✅ Verify Origin/Referer headers
```

---

## 💡 Key Takeaways

| Issue | Prevention |
|-------|-----------|
| **Server-side validation** is NOT optional | Always validate both client and server |
| **Fintech = no tolerance for bugs** | Every bug can cost money and trust |
| **Security testing is QA testing** | Authorization, encryption, and attack simulation matter |
| **Manual testing catches logic bugs** | Automation catches regression; manual finds edge cases |
| **Documentation saves lives** | Clear test cases prevent bugs from slipping through |

---

## 👋 About Me

Hi! I'm **Innara Karim**, a Software Quality Assurance Engineer with **3+ years of hands-on experience** testing web and mobile applications, with a special focus on fintech platforms.

### My Testing Philosophy:
- 🎯 **Detail-oriented:** I believe bugs hide in edge cases
- 🔍 **Practical:** Test cases should reflect real user behavior
- 💡 **Curious:** I dig deep to understand why bugs happen, not just that they exist
- 🤝 **Collaborative:** Great QA is about communication, not just finding bugs

### My Expertise:
- ✅ Manual Testing (Functional, Regression, Sanity, UAT)
- 🔗 API Testing (Postman, Insomnia, Swagger)
- 🤖 Basic Test Automation (Cypress, Selenium)
- 📱 Web & Mobile Testing (iOS, Android)
- 💼 Agile/Scrum environments

### Recent Work:
- Tested fintech applications handling millions in transactions
- Created comprehensive test plans for payment systems
- Automated regression testing for SaaS platforms
- Mentored junior QA engineers on best practices

---

## 🤝 Connect With Me

Let's discuss QA strategies, testing challenges, or opportunities to collaborate!

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/innarakarim/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/innara)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:innara.karim2018@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF6B6B?style=for-the-badge&logo=firefox&logoColor=white)](https://innara-karimm.vercel.app/)

</div>

---

## 📚 Contributing

This is a living document! If you've found bugs I should know about or have test scenarios to add:

1. Open an issue with your bug example
2. Submit a PR with additional test cases
3. Share your experiences in the discussions

---

<div align="center">

### ⭐ If this helped you, give it a star!

*Let's make fintech safer, one test case at a time.* 🚀

*Last updated: April 2026*

</div>