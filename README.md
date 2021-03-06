# Android_Review_1_res
to handle with all the res in android.

![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/output%202.png)

1. to Vetorize all the png or jpeg formated image/graphics, in this way the graphics matches all screen sizes.

   https://www.vectorizer.io
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/vetorization.png)
   
2. then use SVG-XML converter.

   To start Vector Asset Studio:

     1.In Android Studio, open an Android app project.
     
     2.In the Project window, select the Android view.
     
     3.Right-click the res folder and select New > Vector Asset.

     4. Vector Asset Studio appears.

   https://www.twblogs.net/a/5b8ece372b7177188347e26a 
   
   5. or use 3-party svg-vector converter to generate the android tag xml file.
   
   https://romannurik.github.io/AndroidAssetStudio/
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg1.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg2.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg3.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg4.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg5.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg6.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg7.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg8.png)
   
   ![](https://raw.githubusercontent.com/QueenieCplusplus/Android_Review_1_res/main/svg9.png)

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
