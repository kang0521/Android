# Android
Android


package com.example.twoapplybutton
import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity
import com.example.twoapplybutton.R

class MainActivity : AppCompatActivity() {
    lateinit var btn1: Button
    lateinit var btn2: Button
    lateinit var btn3: Button
    lateinit var btn4: Button
    lateinit var btn5: Button
    lateinit var btn6: Button
    lateinit var btn7: Button
    lateinit var btn8: Button
    lateinit var btn9: Button
    lateinit var btn0: Button
    lateinit var btn00: Button
    lateinit var jia: Button
    lateinit var jian: Button
    lateinit var jiahuojian: Button
    lateinit var percentage: Button
    lateinit var cheng: Button
    lateinit var chu: Button
    lateinit var dian: Button
    lateinit var sum: Button
    lateinit var clear: Button
    lateinit var edit: EditText
    private var ss :String= ""
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.frame_layout)
        btn1 = findViewById<Button>(R.id.btn1)
        btn2 = findViewById<Button>(R.id.btn2)
        btn3 = findViewById<Button>(R.id.btn3)
        btn4 = findViewById<Button>(R.id.btn4)
        btn5 = findViewById<Button>(R.id.btn5)
        btn6 = findViewById<Button>(R.id.btn6)
        btn7 = findViewById<Button>(R.id.btn7)
        btn8 = findViewById<Button>(R.id.btn8)
        btn9 = findViewById<Button>(R.id.btn9)
        btn0 = findViewById<Button>(R.id.btn0)
        btn0 = findViewById<Button>(R.id.btn00)// 数字按钮
        jia = findViewById<Button>(R.id.jia)
        jian = findViewById<Button>(R.id.jian)
        jiahuojian = findViewById<Button>(R.id.jiahuojian)
        percentage = findViewById<Button>(R.id.percentage)
        cheng = findViewById<Button>(R.id.cheng)
        chu = findViewById<Button>(R.id.chu)
        dian = findViewById<Button>(R.id.dian)
        sum = findViewById<Button>(R.id.sum)
        clear = findViewById<Button>(R.id.clear) // +号
        edit = findViewById<EditText>(R.id.edit) // 显示⽂本
        //resources
        //xml中⽤@访问资源
        //代码中⽤getResources（）
        btn1.setOnClickListener(Click())
        btn2.setOnClickListener(Click() as View.OnClickListener)
        btn3.setOnClickListener(Click())
        btn4.setOnClickListener(Click())
        btn5.setOnClickListener(Click())
        btn6.setOnClickListener(Click())
        btn7.setOnClickListener(Click())
        btn8.setOnClickListener(Click())
        btn9.setOnClickListener(Click())
        btn0.setOnClickListener(Click())
        btn00.setOnClickListener(Click())
        jia.setOnClickListener(Click())
        jian.setOnClickListener(Click())
        jiahuojian.setOnClickListener(Click())
        percentage.setOnClickListener(Click())
        cheng.setOnClickListener(Click())
        chu.setOnClickListener(Click())
        sum.setOnClickListener(Click())
        dian.setOnClickListener(Click())
        clear.setOnClickListener(Click())
        edit.setOnClickListener(Click())
    }
    // 设置按钮点击后的监听
    inner class Click : View.OnClickListener {
        // lateinit var edit: EditText
// private var ss :String= ""
        override fun onClick(v: View) {
            when (v.getId()) {
                R.id.clear -> {
                    ss = ""
                    edit.setText(ss)
                }
                R.id.btn0 -> {
                    ss += "0"
                    edit.setText(ss)
                }
                R.id.btn00 -> {
                    ss += "00"
                    edit.setText(ss)
                }
                R.id.btn1 -> {
                    ss += "1"
                    edit.setText(ss)
                }
                R.id.btn2 -> {
                    ss += "2"
                    edit.setText(ss)
                }
                R.id.btn3 -> {
                    ss += "3"
                    edit.setText(ss)
                }
                R.id.btn4 -> {
                    ss += "4"
                    edit.setText(ss)
                }
                R.id.btn5 -> {
                    ss += "5"
                    edit.setText(ss)
                }
                R.id.btn6 -> {
                    ss += "6"
                    edit.setText(ss)
                }
                R.id.btn7 -> {
                    ss += "7"
                    edit.setText(ss)
                }
                R.id.btn8 -> {
                    ss += "8"
                    edit.setText(ss)
                }
                R.id.btn9 -> {
                    ss += "9"
                    edit.setText(ss)
                }
                R.id.dian -> {
                    if (ss.length === 0 || ss.indexOf(" ") === ss.length - 3 ||
                        ss.lastIndexOf(".") > ss.indexOf(
                            " "
                        )
                    ) {
                        return
                    } else {
                        ss += "."
                        edit.setText(ss)
                    }
                }
                R.id.jia -> {
                    if (ss.length === 0) {
                        return
                    }
                    if (ss.contains(" ")) {
                        if (!(ss.indexOf(" ") !== ss.length - 3 && ss.indexOf(" ") !== ss.length - 2 && ss.indexOf(
                                " "
                            ) !== ss.length - 1)
                        ) return
                        result
                    }
                    ss += " ＋ "
                    edit.setText(ss)
                }
                R.id.jian -> {
                    if (ss.length === 0) {
                        return
                    }
                    if (ss.contains(" ")) {
                        if (ss.indexOf(" ") === ss.length - 3 || ss.indexOf(" ") === ss.length - 2
                            || ss.indexOf(
                                " "
                            ) === ss.length - 1
                        ) return
                        result
                    }
                    ss += " － "
                    edit.setText(ss)
                }
                R.id.cheng -> {
                    if (ss.length === 0) {
                        return
                    }
                    if (ss.contains(" ")) {
                        if (ss.indexOf(" ") === ss.length - 3 || ss.indexOf(" ") === ss.length - 2
                            || ss.indexOf(
                                " "
                            ) === ss.length - 1
                        ) return
                        result
                    }
                    ss += " × "
                    edit.setText(ss)
                }
                R.id.chu -> {
                    if (ss.length === 0) {
                        return
                    }
                    if (ss.contains(" ")) {
                        if (ss.indexOf(" ") === ss.length - 3 || ss.indexOf(" ") === ss.length - 2
                            || ss.indexOf(
                                " "
                            ) === ss.length - 1
                        ) return
                        result
                    }
                    ss += " / "
                    edit.setText(ss)
                }
                R.id.sum -> result
            }
        }
        private val result: Unit
            private get() {
                var result = 0.0
                if (ss == null || ss.equals("")) return
                if (!ss.contains(" ")) return
                val s1: String = ss.substring(0, ss.indexOf(" "))
                val op: String = ss.substring(ss.indexOf(" ") + 1, ss.indexOf(" ") + 2)
                val s2: String = ss.substring(ss.indexOf(" ") + 3)
                if (s1 != "" && s2 != "") {
                    val d1 = s1.toDouble()
                    val d2 = s2.toDouble()
                    when (op) {
                        "＋" -> result = d1 + d2
                        "－" -> result = d1 - d2
                        "×" -> result = d1 * d2
                        "÷" -> {
                            if (d2 == 0.0) {
                                edit.setText("不能除以零")
                            }
                            result = d1 / d2 * 1.0
                        }
                    }
                    val r = result.toInt()
                    if (r.toDouble() == result) {
                        edit.setText("" + r)
                        ss = "" + r
                    } else {
                        edit.setText(result.toString() + "")
                        ss = "" + result
                    }
                }
            }
    }
}

<?xml version="1.0" encoding="utf-8"?>
<GridLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:rowCount="6"
    android:columnCount="4"
    android:orientation="horizontal">

    <EditText
        android:id="@+id/edit"
        android:layout_width="350dp"
        android:layout_height="wrap_content"
        android:layout_columnSpan="4"
        android:layout_marginLeft="4px"
        android:gravity="right"
        android:hint="@string/app_name"
        android:textColor="@color/black"
        android:textSize="50dp" />


    <Button
        android:id="@+id/clear"
        android:layout_height="wrap_content"
        android:text="c"
        android:textSize="26sp" />
    <Button
        android:id="@+id/jiahuojian"
        android:text="+/-"
        android:textSize="26sp" />

    <Button
        android:id="@+id/percentage"
        android:text="%"
        android:textSize="26sp" />

    <Button
        android:id="@+id/chu"
        android:text="/"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn7"
        android:text="7"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn8"
        android:text="8"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn9"
        android:text="9"
        android:textSize="26sp" />

    <Button
        android:id="@+id/cheng"
        android:text="*"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn4"
        android:text="4"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn5"
        android:text="5"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn6"
        android:text="6"
        android:textSize="26sp" />

    <Button
        android:id="@+id/jian"
        android:text="-"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn1"
        android:text="1"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn2"
        android:text="2"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn3"
        android:text="3"
        android:textSize="26sp" />

    <Button
        android:id="@+id/jia"
        android:text="+"
        android:textSize="26sp" />
    <Button
        android:id="@+id/btn0"
        android:text="0"
        android:textSize="26sp" />

    <Button
        android:id="@+id/btn00"
        android:text="00"
        android:textSize="26sp" />

    <Button
        android:id="@+id/dian"
        android:text="."
        android:textSize="26sp" />

    <Button
        android:id="@+id/sum"
        android:text="="
        android:textSize="26sp" />
</GridLayout>
