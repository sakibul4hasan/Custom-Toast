# Custom-Toast





### Step 1. Create a Custom Layout for the Toast:

- Create an XML layout file for your custom toast. For example, you can create a file named custom_toast_layout.xml in the res/layout directory:


```bash
<androidx.cardview.widget.CardView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:orientation="horizontal"
    app:cardCornerRadius="6dp">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:background="#FF4081"
        android:paddingHorizontal="6dp"
        android:paddingVertical="5dp"
        >


    <ImageView
        android:id="@+id/custom_toast_image"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginRight="7dp"
        android:contentDescription="Custom Icon"/>

    <TextView
        android:id="@+id/custom_toast_text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textColor="#FFFFFF"
        />

    </LinearLayout>

</androidx.cardview.widget.CardView>
```









### Step 2. Create a Custom Toast Class:
- Create a Java class for your custom toast. Here's an example:

```bash
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

public class CustomToast {

    public static void showCustomToast(Context context, String message, int imageResource) {
        // Inflate the custom layout
        View view = LayoutInflater.from(context).inflate(R.layout.custom_toast_layout, null);

        // Get references to the views in the custom layout
        ImageView imageView = view.findViewById(R.id.custom_toast_image);
        TextView textView = view.findViewById(R.id.custom_toast_text);

        // Customize the views
        imageView.setImageResource(imageResource);
        textView.setText(message);

        // Create and show the custom toast
        Toast toast = new Toast(context);
        toast.setDuration(Toast.LENGTH_SHORT);
        toast.setView(view);
        toast.show();
    }
}
```








### Step 3.
- In your activity, when handling a click event, call showCustomToast and pass the image resource ID along with the message:

```bash

        CustomToast.showCustomToast(YourActivity.this, "Clicked!", R.drawable.your_toast_icon_image);

```
