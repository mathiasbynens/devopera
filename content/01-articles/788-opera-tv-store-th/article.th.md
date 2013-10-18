Title: เทมเพลตแอป Opera TV Store 
----
Date: 2012-10-17 12:20:56
----
Lang: th
----
Author: 
----
License: Creative Commons Attribution 3.0 Unported
----
License_url: http://creativecommons.org/licenses/by/3.0/
----
Text:

<h2>ข้อมูลเบื้องต้น</h2>

<p>ตั้งแต่การเปิดตัว Opera TV Store เราได้เห็นผู้สร้างเผยแพร่แอปต่างๆ มากมายและผู้ใช้ก็ชื่นชอบ ความจริงแล้วแอป TV ของเราสร้างขึ้นโดยใช้มาตรฐานเว็บซึ่งหมายถึงนักพัฒนาเว็บทั้งหลายสามารถใช้ทักษะของตนที่มีอยู่เพื่อสร้างเนื้อหาสำหรับแพลตฟอร์ม TV ได้  แต่การพัฒนาสำหรับ TV ยังไม่เป็นที่่คุ้นเคยเท่าใดนัก ดังนั้น เพื่อให้ง่ายขึ้น เราจึงได้สร้างเทมเพลตบางอย่างสำหรับแอปทั่วไปที่พบได้บ่อยๆ ที่ผู้สร้างเนื้อหาจะสามารถใช้ได้อย่างอิสระ </p>

<p>ข่าวสารและความบันเทิงจัดอยู่ในประเภทเนื้อหาที่นิยมที่สุดในทุกเพลตฟอร์ม ดังนั้นเทมเพลตที่เรามีให้จึงเป็นแอปสำหรับเครื่องเล่นวิดีโอและ RSS reader   ทั้งสองประเภทนี้มีไว้เพื่อให้ง่ายต่อการกำหนดรูปแบบเอง ดังนั้นคุณจึงสามารถเผยแพร่แอปที่เป็นแบรนด์ของตนเองได้อย่างรวดเร็วโดยไม่ต้องกังวลเรื่องเวลาและค่าใช้จ่ายในการพัฒนาแอป </p>

<h2>เทมเพลตสำหรับเครื่องเล่นวิดีโอ</h2>

<p>
<img src="http://devfiles.myopera.com/articles/9442/video-app-template.jpg" alt="ภาพหน้าจอที่แสดงแอป TV สำหรับเครื่องเล่นวิดีโอที่กำลังใช้งานอยู่" />
</p>
<p class="caption">ภาพที่ 1: เทมเพลต TV สำหรับเครื่องเล่นวิดีโอที่กำลังใช้งานอยู่ </p>

<h3>ภาพรวม</h3>

<p>เทมเพลตแอปวิดีโอเป็นอะไรที่มากกว่าการเล่นวิดีโอธรรมดา ที่ทำให้คุณสามารถแยกวิดีโอเป็นช่องต่างๆ ตามธีมหรือหัวข้อได้ ยังมีคุณสมบัติในตัวในการใส่บุ๊คมาร์คที่ผู้ใช้สามารถย้ายวิดีโอที่พวกเขาชอบเป็นพิเศษไปไว้ในรายการโปรดของพวกเขาได้อีกด้วย  เมื่อชมวิดีโอ ผู้ใช้ยังสามารถเลือกที่จะเล่นวิดีโออย่างต่อเนื่องหรือแม้แต่สลับลำดับเรื่องที่เล่นก็ได้ เพื่อกำหนดค่าของเทมเพลตเอง มีสามเรื่องหลักๆ ที่สามารถแก้ไขได้ง่ายๆ นั่นคือ ข้อมูล (ซึ่งทำได้ผ่านไฟล์ XML หรือ API ที่มีอยู่ของคุณ), ภาพและสี </p>

<h3>การกำหนดค่าเอง</h3>

<p>สิ่งแรกที่คุณควรทำก็คือการเพิ่มวิดีโอและช่องต่างๆ ที่คุณเลือกไว้  ซึ่งจะทำในไฟล์ <code>video.xml</code> ซึ่งจะมีลักษณะดังนี้:</p>

<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;rss&gt;
  &lt;channel&gt;
    &lt;item&gt;
      &lt;title&gt;Opera Labs: Mobile Extensions&lt;/title&gt;
      &lt;description&gt;We&#39;re excited to share with you a Labs release of our mobile browser with support for extensions.&lt;/description&gt;
      &lt;category&gt;Opera Labs&lt;/category&gt;
      &lt;duration&gt;00:01:24&lt;/duration&gt;
      &lt;content url=&quot;http://apps.tvstore.opera.com/videos/Opera_Labs_Mobile_Extensions.mp4&quot; fileSize=&quot;24434480&quot; type=&quot;video/mp4&quot; /&gt;
      &lt;thumbnail url=&quot;http://apps.tvstore.opera.com/videos/Opera_Labs_Mobile_Extensions.jpg&quot; width=&quot;250&quot; height=&quot;140&quot; /&gt;
    &lt;/item&gt;
  &lt;/channel&gt;
&lt;/rss&gt;</code></pre>

<p>ไฟล์นี้จะถูกอ่านโดยฟังก์ชัน <code>getData()</code> ในไฟล์ <code>videotemplate.js</code> ดังนั้น ถ้าคุณต้องการใช้ API หรือ RSS feed ของคุณเองเป็นต้นฉบับของวิดีโอ คุณก็แค่เปลี่ยนที่อยู่ไฟล์ในฟังก์ชันนั้น  คุณอาจจะต้องเปลี่ยนกฎการตรวจสอบโครงสร้างของประโยคในฟังก์ชัน <code>prepareData()</code> ที่อยู่ในไฟล์เดียวกันเพื่อให้เหมาะสม</p>

<p>สำหรับการกำหนดค่าการมองเห็น ภาพทั้งหมดจะอยู่ในสารบบ <code>images</code> และตั้งชื่อไฟล์ให้สมเหตุสมผล อย่างเช่น <code>logo.png</code>  ซึ่งจะทำให้คุณสามารถเปลี่ยนชื่อเป็นโลโก้และสีของคุณเองได้ง่ายๆ นอกจากนี้ สไตล์ต่างๆ สำหรับการออกแบบแอปจะอยู่ในไฟล์ <code>style.css</code> ในสารบบ <code>css</code>  การกำหนดฟอนต์และสีจะอยู่ที่ด้านบนของไฟล์นี้เพื่อทำให้สามารถกำหนดค่าเองได้ง่ายๆ </p>

<h2>เทมเพลต RSS reader </h2>

<p>
<img src="http://devfiles.myopera.com/articles/9442/rss-app-template.jpg" alt="ภาพหน้าจอที่แสดงแอป TV สำหรับ RSS reader ที่กำลังใช้งานอยู่" />
</p>
<p class="caption">ภาพที่ 2: แอป TV สำหรับ RSS reader ที่กำลังใช้งานอยู่</p>

<h3>ภาพรวม</h3>

<p>เทมเพลตแอป RSS reader ทำให้คุณนำเสนอข่าวสารหรือเนื้อหาอื่นๆ ที่มีการอัพเดทเป็นประจำได้อย่างสะดวกสบายในแอปเดียว เช่นเดียวกับเทมเพลตแอปวิดีโอที่สามารถควบคุมได้ง่ายๆ ด้วยคีย์คำสั่งบนรีโมทคอนโทรล TV และมีคุณสมบัติโชว์สไลด์ที่สามารถเล่นรายการข่าวหรือบทความทีละรายการได้โดยอัตโนมัติ  การกำหนดค่าเองประกอบด้วยการเปลี่ยนสีง่ายๆ หรือการเปลี่ยนค่าขั้นสูง อย่างเช่น การแก้ไข HTML ที่สร้างขึ้นแบบไดนามิก</p>

<h3>การกำหนดค่าเอง</h3>

<p>ขั้นตอนสำคัญที่สุดคือการกำหนดค่าการฟีดที่คุณต้องการจะใช้  ซึ่งทำได้ด้วยการแก้ไขแถวลำดับ <code>DEF_FEEDS</code> ในไฟล์ <code>js/config.js</code>  คุณสามารถเพิ่มจำนวนได้เท่าที่ต้องการ รวมถึงจำนวนฟีดที่โฮสต์อยู่บนโดเมนภายนอก อย่างไรก็ตาม การแก้ไขมาตรการความปลอดภัยของเบราวเซอร์จำเป็นต้องใช้พร็อกซี่เซิร์ฟเวอร์สำหรับฟีด ซึ่งจะมีคำแนะนำในการตั้งค่านี้ในโปรแกรมการสอน ที่ลิงก์กับแพ็คเกจที่สามารถดาวน์โหลดได้ด้านล่างนี้  รายการฟีดอาจมีลักษณะดังนี้คือ</p>

<pre><code>var DEF_FEEDS = [{
  url: &#39;data/data.xml&#39;
},
{
  url: &#39;http://my.opera.com/chooseopera/xml/rss/blog/&#39;,
  proxy: true
}];</code></pre>

<p>และในไฟล์ <code>js/config.js</code> จะมีตัวเลือกต่างๆ ในการเปลี่ยนชื่อแอปและที่อยู่พร็อกซี่เซิร์ฟเวอร์ของคุณ ถ้าจำเป็น</p>

<pre><code>/**
 * Application main title 
 */
var APP_TITLE = &#39;All feeds&#39;;

/**
 * Proxy URL
 */
var PROXY_URL = &#39;/xhrproxy/?_proxy_url=&#39;;</code></pre>

<p>สามารถเปลี่ยนสไตล์ในการดูแอปได้ด้วยการแก้ไขไฟล์ <code>css/common.css</code> และถ้าคุณต้องการแก้ไข HTML ที่แต่ละรายการฟีดใช้ ก็จะมีอยู่ในไฟล์ <code>js/Item.js</code> ในแถวลำดับ <code>TMPL</code> และ <code>TMPL_CONTENT</code> </p>

<h2>ดาวน์โหลดเทมเพลต!</h2>

<p>เทมเพลตแอปมีให้ดาวน์โหลดได้ที่นี่ (ไฟล์ ZIP):</p>

<ul>
    <li><a href="http://apps.tvstore.opera.com/templates/videotemplate.zip">เทมเพลตแอปวิดีโอ</a></li>
    <li><a href="http://apps.tvstore.opera.com/templates/rssreader.zip">เทมเพลตแอป RSS reader</a></li>
</ul>

<p>ไฟล์ ZIP ทั้งสองนี้จะมีการสอนที่ละเอียดยิ่งขึ้นในเรื่องการเพิ่มข้อมูลของคุณเองและการกำหนดค่าเทมเพลตเองเพื่อให้เหมาะกับรสนิยมหรือแนวทางแบรนด์ของคุณ  ซึ่งได้รับการออกแบบเพื่อให้คุณไม่ต้องแก้ไขฟังก์ชันการทำงานหรือเลย์เอาท์ใดๆ เพื่อสร้างแอปที่ดูดีและใช้งานง่าย อย่างไรก็ดี เนื่องจากเทมเพลตทั้งสองนี้อนุญาตให้ใช้งานได้ฟรีแบบโอเพ่นซอร์ส คุณจึงสามารถเปลี่ยนรหัสในระดับลึกได้เท่าที่คุณต้องการ โดยไม่มีใครห้าม  เราจะรอดูแอปที่คุณสร้างจากเทมเพลตเหล่านี้ใน Opera TV Store!</p>

<p class="note">เทมเพลตต่างๆ นี้ได้รับการอนุญาตภายใต้ใบอนุญาต Creative Commons Attribution 3.0 Unported  โปรดใส่คำประกาศนี้ไว้ในเอกสารที่แจกทุกฉบับ: ลิขสิทธิ์ © 2012 Opera Software ASA. ใช้ภายใต้การอนุญาตเท่านั้น</p>