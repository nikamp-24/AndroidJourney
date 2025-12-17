\# 📅 Day 5 --- Input Widgets (Android with Java)

\## 🎯 Goal of Day 5

Learn how users enter data into Android apps using input widgets like \`EditText\`, handle passwords, manage the keyboard, and build a simple login form.

\---

\## 1️⃣ What are Input Widgets?

\*\*Input widgets\*\* are UI components that allow users to enter data.

Common use cases:

\- Login

\- Signup

\- Search

\- Forms

\- Feedback

\### Common Input Widgets

\- \`EditText\`

\- \`TextInputEditText\`

\- \`TextInputLayout\`

\- \`Button\`

\---

\## 2️⃣ EditText Basics

\`EditText\` is used to take input from the user.

\### Basic Example

\`\`\`xml

android:layout\_width="match\_parent"

android:layout\_height="wrap\_content"

android:hint="Enter your name"

android:inputType="text" />

3️⃣ EditText Input Types

The inputType attribute controls what kind of data the user can enter.

inputTypePurpose

textNormal text

textEmailAddressEmail input

numberNumbers only

phonePhone number

textPasswordPassword

numberPasswordNumeric password

textMultiLineLong text

Email Input Example

xml

Copy code

android:hint="Email"

android:inputType="textEmailAddress" />

4️⃣ Password Fields

Simple Password Field

xml

Copy code

android:hint="Password"

android:inputType="textPassword" />

✔ Characters appear as dots

✔ Keyboard switches to password mode

5️⃣ Material Password Field (Recommended)

xml

Copy code

android:layout\_width="match\_parent"

android:layout\_height="wrap\_content">

android:layout\_width="match\_parent"

android:layout\_height="wrap\_content"

android:hint="Password"

android:inputType="textPassword" />

Benefits

Floating labels

Error handling

Modern UI

Used in real apps

6️⃣ Keyboard Handling

Hide Keyboard Programmatically

java

Copy code

InputMethodManager imm =

(InputMethodManager) getSystemService(Context.INPUT\_METHOD\_SERVICE);

imm.hideSoftInputFromWindow(view.getWindowToken(), 0);

Keyboard Action Button

xml

Copy code

android:imeOptions="actionDone"
