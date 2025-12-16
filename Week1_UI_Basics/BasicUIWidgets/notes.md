# **Android UI Widgets - Basic Overview**

Today we'll explore the fundamental building blocks of Android user interfaces.

## **Core UI Widgets**

### **1. TextView** 📝

*Displays text to the user*

```xml

<TextView

    android:id="@+id/textView"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"

    android:text="Hello Android!"

    android:textSize="18sp"

    android:textColor="#000000"/>

```

**Common Attributes:**

- `text`: The text content

- `textSize`: Size in `sp` (scale-independent pixels)

- `textColor`: Text color

- `textStyle`: `bold`, `italic`, `normal`

### **2. EditText** ✏️

*Text input field for user*

```xml

<EditText

    android:id="@+id/editText"

    android:layout_width="match_parent"

    android:layout_height="wrap_content"

    android:hint="Enter your name"

    android:inputType="textPersonName"/>

```

**Input Types:**

- `textPassword`: For passwords

- `number`: Numeric input

- `phone`: Phone numbers

- `textEmailAddress`: Email input

### **3. Button** 🔘

*Clickable button*

```xml

<Button

    android:id="@+id/button"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"

    android:text="Click Me"

    android:onClick="onButtonClick"/>

```

### **4. ImageView** 🖼️

*Displays images*

```xml

<ImageView

    android:id="@+id/imageView"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"

    android:src="@drawable/ic_launcher"

    android:scaleType="centerCrop"/>

```

### **5. CheckBox** ☑️

*Selection control*

```xml

<CheckBox

    android:id="@+id/checkBox"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"

    android:text="Accept terms"/>

```

### **6. RadioButton & RadioGroup** 🔘

*Single selection from multiple options*

```xml

<RadioGroup

    android:id="@+id/radioGroup"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content">

    <RadioButton

        android:id="@+id/radioOption1"

        android:layout_width="wrap_content"

        android:layout_height="wrap_content"

        android:text="Option 1"/>

    <RadioButton

        android:id="@+id/radioOption2"

        android:layout_height="wrap_content"

        android:layout_width="wrap_content"

        android:text="Option 2"/>

</RadioGroup>

```

### **7. Switch** 🔄

*Toggle switch*

```xml

<Switch

    android:id="@+id/switchWidget"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"

    android:text="Enable Feature"/>

```

### **8. ProgressBar** ⏳

*Shows progress*

```xml

<!-- Indeterminate (spinning) -->

<ProgressBar

    android:id="@+id/progressBar"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"/>

<!-- Determinate (horizontal) -->

<ProgressBar

    android:id="@+id/progressBarHorizontal"

    style="?android:attr/progressBarStyleHorizontal"

    android:layout_width="match_parent"

    android:layout_height="wrap_content"

    android:max="100"

    android:progress="50"/>

```

### **9. SeekBar** 🎚️

*Draggable slider*

```xml

<SeekBar

    android:id="@+id/seekBar"

    android:layout_width="match_parent"

    android:layout_height="wrap_content"

    android:max="100"/>

```

### **10. RatingBar** ⭐

*Star rating*

```xml

<RatingBar

    android:id="@+id/ratingBar"

    android:layout_width="wrap_content"

    android:layout_height="wrap_content"

    android:numStars="5"

    android:stepSize="0.5"/>

```

## **Best Practices**

1\. **Use meaningful IDs**: `btnSubmit` vs `button1`

2\. **Consistent sizing**: Use `dp` for dimensions, `sp` for text

3\. **Provide hints**: Use `android:hint` in EditText

4\. **Handle empty states**: Validate user input

5\. **Accessibility**: Add `contentDescription` for images

6\. **Internationalization**: Use string resources instead of hardcoded text
