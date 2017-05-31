#  내가 첫번째로 만든 게산기 

```java
package com.guozhe.android.gyesangi;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    Button button0,button1,button2,button3,button4,button5
            ,button6,button7,button8,button9
            ,add,sub,mul,div,eq,point
            ,backspace,cleard;
    TextView tv;
    boolean over=false;
    int i;
    double number1=0,number2=0,result=0;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        for(int i=0;i<10;i++){
            int id=getResources().getIdentifier("button"+i,"id",getPackageName());
            findViewById(id).setOnClickListener(this);
        }

        findViewById(R.id.add).setOnClickListener(this);
        findViewById(R.id.sub).setOnClickListener(this);
        findViewById(R.id.mul).setOnClickListener(this);
        findViewById(R.id.div).setOnClickListener(this);
        findViewById(R.id.point).setOnClickListener(this);
        findViewById(R.id.backspace).setOnClickListener(this);
        findViewById(R.id.eq).setOnClickListener(this);
        findViewById(R.id.cleared).setOnClickListener(this);
        tv=(TextView)findViewById(R.id.tv);



    }

    @Override
    public void onClick(View v) {
        switch(v.getId()){
            case R.id.backspace:
                String myStr = tv.getText().toString();
                try{
                    tv.setText(myStr.substring(0,myStr.length()-1));
                }catch (Exception e){
                    tv.setText("");
                }
                break;
            case R.id.button0:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString = tv.getText().toString();
                myString +="0";
                tv.setText(myString);
                break;
            case R.id.button1:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString1 = tv.getText().toString();
                myString1 +="1";
                tv.setText(myString1);
                break;
            case R.id.button2:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString2 = tv.getText().toString();
                myString2 +="2";
                tv.setText(myString2);
                break;
            case R.id.button3:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString3 = tv.getText().toString();
                myString3 +="3";
                tv.setText(myString3);
                break;
            case R.id.button4:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString4 = tv.getText().toString();
                myString4 +="4";
                tv.setText(myString4);
                break;
            case R.id.button5:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString5 = tv.getText().toString();
                myString5 +="5";
                tv.setText(myString5);
                break;
            case R.id.button6:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString6 = tv.getText().toString();
                myString6 +="6";
                tv.setText(myString6);
                break;
            case R.id.button7:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString7 = tv.getText().toString();
                myString7 +="7";
                tv.setText(myString7);
                break;
            case R.id.button8:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString8 = tv.getText().toString();
                myString8 +="8";
                tv.setText(myString8);
                break;
            case R.id.button9:
                if(over){
                    tv.setText(null);
                    over=false;
                }
                String myString9 = tv.getText().toString();
                myString9 +="9";
                tv.setText(myString9);
                break;
            case R.id.add:
                String stringAdd=tv.getText().toString();
                if(stringAdd.equals(null)){
                    return;
                }
                number1=Double.valueOf(stringAdd);
                tv.setText(null);
                i=1;
                over=false;
                break;
            case R.id.sub:
                String stringsub=tv.getText().toString();
                if(stringsub.equals(null)){
                    return;
                }
                number1=Double.valueOf(stringsub);
                tv.setText(null);
                i=2;
                over=false;
                break;
            case R.id.mul:
                String stringmul=tv.getText().toString();
                if(stringmul.equals(null)){
                    return;
                }
                number1=Double.valueOf(stringmul);
                tv.setText(null);
                i=3;
                over=false;
                break;
            case R.id.div:
                String stringdiv=tv.getText().toString();
                if(stringdiv.equals(null)){
                    return;
                }
                number1=Double.valueOf(stringdiv);
                tv.setText(null);
                i=4;
                over=false;
                break;
            case R.id.eq:
                String stringeq=tv.getText().toString();
                if(stringeq.equals(null)){
                    return;
                }
                number2=Double.valueOf(stringeq);
                tv.setText(null);
                switch (i){
                    case 0:
                        result=number2;
                    case 1:
                        result=number1+number2;
                        break;
                    case  2:
                        result=number1-number2;
                        break;
                    case 3:
                        result=number1*number2;
                        break;
                    case 4:
                        result=number1/number2;
                        break;
                }
                tv.setText(String.valueOf(result));
                over=true;
                break;



        }

    }
}
```
