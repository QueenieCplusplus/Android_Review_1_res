# Android_Review_1_res
to handle with all the res in android.

![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/output%202.png)

1. to Vetorize all the png or jpeg formated image/graphics, in this way the graphics matches all screen sizes.

   https://www.vectorizer.io
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/vetorization.png)
   
2. then use SVG-XML converter.

   https://products.aspose.app/pdf/conversion/svg-to-xml
   
   https://developer.android.com/reference/android/graphics/drawable/BitmapDrawable (Bitmap)

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


4. code.

            package com.katepatty.luckyroller

         import androidx.appcompat.app.AppCompatActivity
         import android.os.Bundle
         import android.util.Log.d
         import android.widget.ImageView
         import android.widget.TextView
         import kotlinx.android.synthetic.main.activity_main.*

         class MainActivity : AppCompatActivity() {

             override fun onCreate(savedInstanceState: Bundle?) {
                 super.onCreate(savedInstanceState)
                 setContentView(R.layout.activity_main)

                 roller()

             }

             private fun roller(){

                 // 宣告容器變數
                 val outputStr: TextView = findViewById(R.id.rollResultTxt)
                 val outputImg: ImageView = findViewById(R.id.rollResultImg)

                 // 生出隨機值
                 val randomInt = (1..4).random()

                 // 將隨機值指派給容器變數的屬性中
                 //outputStr.text = randomInt.toString()
                 //rollResultTxt. got its method too

                 val randomTxt = when (randomInt){

                     1 -> "好運連連"
                     2 -> "貴人加持"
                     3 -> "喜憂參半"
                     else -> "請回府，記得拜拜喔！下次再來玩～"

                 }

                 val randomSrc = when (randomInt) {

                     1 -> R.drawable.notbad
                     2 -> R.drawable.home
                     3 -> R.drawable.gotpower
                     4 -> R.drawable.backhome
                     else -> R.drawable.luck

                 }
                 // below resId = 容器變數放回呼值
                 outputImg.setImageResource(randomSrc)
                 outputStr.setText(randomTxt)

             }
         }
