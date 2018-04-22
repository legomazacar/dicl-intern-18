### DICL Internship Program 2018

สวัสดีน้องๆที่ให้ความสนใจมาฝึกงานที่บริษัท ดิจิตอล อินไซด์เดอร์ จำกัด ในปี 2018 นี้ทุกๆคนนะครับ ก่อนที่จะเข้ามาฝึกงานกับเรา พี่มีบททดสอบเล็กน้อยเพื่อวัดทักษะพื้นฐานสำหรับนักพัฒนา Mobile Developer น้องๆไม่จำเป็นต้องตอบหรือต้องรู้ทุกเรื่องในบททดสอบนี้ เพราะเรามาสามารถมาเรียนรู้กันภายหลังได้ เพียงแต่เราอยากให้น้องๆทุกคนลองทำด้วยตัวเอง ค้นคว้าเอง ทั้งหมดก็เพื่อประโยชน์ของตัวน้องๆเองและบริษัท หากใครสนใจส่งคำตอบกันมานะได้เลยนะครับ ปิดรับสมัครวันที่ 8 เมษายน 18 เวลา 23:59 น.

## 1. Code in Swift or Java / Kotlin
แบบทดสอบนี้จะดูทักษะความรู้ความเข้าใจเกี่ยวกับเรื่อง Collection เช่น Array, Dictionary เป็นต้น

ดาวน์โหลดข้อมูล [data.json](https://github.com/memogames/dicl-intern-18/blob/master/data.json) และเขียนโค้ดเพื่อหาคำตอบ
- 1.1 หาคะแนนเฉลี่ย **score** ของนักเรียน
- 1.2 แสดงชื่อและเกรดของนักเรียนที่ได้คะแนนมากว่า 70 ขึ้นไป
- 1.3 ค้นหาชื่อนักเรียนที่มีคะแนนมากที่สุดและต่ำที่สุด **score**

คำตอบ:
```
package test;

import java.util.ArrayList;
import org.json.JSONObject;
import org.json.JSONArray;
import java.util.HashMap;


public class TEST {

    public static void main(String[] args){
     
        try {  
            
        String strJSON = "[{\"name\":\"John\",\"score\":\"75\",\"grade\":\"B\"}" +

                         ",{\"name\":\"Roy\",\"score\":\"82\",\"grade\":\"A\"}" +
             
                         ",{\"name\":\"Mcqueen\",\"score\":\"72\",\"grade\":\"B\"}" +
             
                         ",{\"name\":\"Stain\",\"score\":\"54\",\"grade\":\"D\"}" +
             
                         ",{\"name\":\"Tron\",\"score\":\"60\",\"grade\":\"C\"}" +
             
                         ",{\"name\":\"Boss\",\"score\":\"91\",\"grade\":\"A\"}]";

     JSONArray data = new JSONArray(strJSON);
       
    ArrayList<HashMap<String,String>> list = new ArrayList<HashMap<String,String>>();
    HashMap<String ,String> pointer;  
     
    
           for (int i = 0; i < data.length(); i++) {
                   JSONObject c = data.getJSONObject(i);
             
                     pointer = new HashMap<String ,String>();  
                     pointer.put("name",c.getString("name")); 
                     pointer.put("score",c.getString("score"));
                     pointer.put("grade",c.getString("grade")); 
                     list.add(pointer);
                     }
           for (int i = 0; i < list.size(); i++) {
               String name = list.get(i).get("name").toString();
               String score =list.get(i).get("score").toString();
               String grade =list.get(i).get("grade").toString();
             
               System.out.println("name : "+name);
               System.out.println("score : "+score);
               System.out.println("grade : "+ grade);       
               
           }
         
       }catch (Exception e) { 
            e.printStackTrace();
       }
    }
 
```

## 2. Create Simple Mobile Application

แบบทดสอบนี้จะดูทักษะความรู้ความเข้าใจสำหรับการพัฒนาแอปพลิเคชั่น และการใช้ UI พื้นฐานของแต่ละ Platform

### Features
- GET ข้อมูล JSON จาก [movie.json](https://github.com/memogames/dicl-intern-18/blob/master/movie.json)
- แสดงรายชื่อและรูปภาพใน ListView หรือ TableView
- ผู้ใช้สามารถกดเพื่อดูข้อมูลรายละเอียดได้ในหน้าถัดไป
- ผู้ใช้สามารถแชร์ข้อมูลชื่อหนังที่สนใจให้กับเพื่อนๆได้
- ออกแบบ UI ได้ตามความต้องการ
- ใช้ Library เพิิ่มเติิมได้

### Technical
- ดาวน์โหลดข้อมูล JSON
- เครื่องมือที่ใช้ Android Studio หรือ Xcode.

## 3. Tiny Question

Q1: Firebase คืออะไร มีฟังก์ชั่นที่น้องๆชื่นชอบนอะไรบ้างและเพราะอะไร (อย่างน้อย 3 ฟังก์ชั่น)

```
A1:Firebase เป็น Project ถูกออกแบบมาให้เป็น API และ Cloud Storage สำหรับพัฒนา Realtime Application 
 รองรับหลาย Platform เบื้องต้นล่าสุดก็มีให้ใช้พัฒนาด้วยกัน 3 Platform คือ IOS App, Android App, Web App
ฟังก์ชั่นที่ชอบ
 1.Firebase Analytics เพราะช่วยวิเคราะห์ข้อมูล 
 2.Firebase Storage   เพราะช่วยในการจัดเก็บข้อมูล
 3.Firebase Cloud Messaging (FCM) เพราะ มีระบบส่งข้อความแจ้งเตือน ใช้งานฟรีไม่จำกัดปริมาณข้อความ และข้ามแพลตฟอร์มได้
```

Q2: REST API คืออะไร

```
A2:REST คือ การสร้าง Webservice ชนิดหนึ่งที่ใช้สื่อสารกันบน Internet ใช้หลักการแบบ stateless 
 คือไม่มี session ซึ่งต่างจาก webservice แบบอื่นเช่น WSDL และ SOAP การทำงานของ RESTful Webservice
 จะอาศัย URI/URL ของ request เพื่อค้นหาและประมวลผลแล้วตอบกลับไปในรูป XML, HTML, JSON  โดย response
 ที่ตอบกลับจะเป็นการยืนยันผลของคำสั่งที่ส่งมา และสามารถพัฒนาด้วยภาษา programming ได้หลากหลาย คำสั่งก็จะมีตาม HTTP verbs
```

Q3: หากต้องสร้างแอปพลิเคชั่น 1 ตัว เพื่อให้รองรับทั้งระบบ iOS และ Android วิิธีไหนที่น้องๆอยากเลือกใช้พัฒนาระหว่าง Native App กับ Cross Platform และเพราะอะไร 

```
A3:เพราะ Cross Platform สามารถทำงานได้หลายระบบ โดยการเขียนแค่ครั้งเดียว
```

Q4: ถ้าให้เลือกได้ 1 บ้าน น้องๆอยากอยู่บ้านไหนระหว่าง Apple , Google และ Microsoft

```
A4:Google
```

Q5: เวลาว่างสิ่งที่ชอบทำที่สุดคืออะไร 2 อันดับแรก

```
A5:1.เล่นเกม 2.ดูYoubetube
```

Q6: แอปพลิเคชั่นไหนบนมือถือที่ชอบที่สุดและเกียจที่สุดตั้งแต่เคยใช้งานมา (ไม่รวมเกมส์) เพราะอะไร

```
A6:ไม่มี เพราะ มือถือใช้แค่โทรเข้า-โทรออก กับส่งข้อความfacebook
```

Q7: อะไรบ้างที่น้องๆคาดว่าจะได้รับในขณะที่ฝึกงานกับพวกเรา?

```
A7:ประสบการณ์และความรู้ที่จะสามารถนำมาต่อยอดได้
```

## Submitting

ให้น้องๆ fork repo นี้แล้วตอบคำถาม จากนั้นส่ง repo มาที่ อีเมลล์ memo.games@gmail.com
