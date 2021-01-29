# Android_Review_1_res
to handle with all the res in android.

![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/output%202.png)

1. to Vetorize all the png or jpeg formated image/graphics, in this way the graphics matches all screen sizes.

   https://www.vectorizer.io
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/vetorization.png)
   
2. then use SVG-XML converter.

   https://products.aspose.app/pdf/conversion/svg-to-xml

2. drag them to res/drawable.

   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/drag%20res.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/path.png)

3. use them in xml layout file.

         <ImageView
         android:id="@+id/dice_image"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_gravity="center_horizontal"
         android:src="@drawable/dice_1" />

