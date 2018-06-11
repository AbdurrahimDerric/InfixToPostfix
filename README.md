# InfixToPostfix

converting an infix statement  into postfix using stack, and then solving the postfix statement using stack also.

15011112
Abdurrahim DERRIC 
Final odev







Yontem 
Problem tanimi:
Verilen bir denklem seti icin  denklemleri teker teker postfix formuna  stack yapisinin yardimiyla donusturerek ve yine stack yapisi kullanarak elde edilen postfix statemente'ini cozmek.  

Cozum:
Infix-to-Postfix donusumu :

İşlem Adımları : 
3. Değişken isimlerini tek karakterlik alarak;
4. Giriş stringindeki sayı olan karakterlerin sayı karşılığını elde etmek için bir fonksiyon yazilir. Aritmetik işlemlerde ve işlem sonuçlarında   9’dan büyük sayılar olabilir .
5. Kullanılan işaretleri  şunlar olabilir :  +  -*  /  (  ) 
6. Yanlış giriş yapılmadığı varsayılmaktadır. 
7. Aritmetik işlemi  denklemde  "= " işaretinin sonrasından başlayarak soldan sağa doğru değerlendililr.


 Stack mantigi:
Eğer o anda bakılan bilgi: 
 sol parantez ise : sol parantez yığına  push edilir. 
 sağ parantez ise :sol parantez  çıkana kadar yığından pop işlemi yapılır. Alınan işlem işareti postfix ifadeye eklenir. Sol parantez görüldüğünde pop işlemine son verilir. Not : Parantezler postfix’e eklenmez.
 sayı ise :postfix ifadeye eklenir. Bir rakamdan fazla olabilir








 işlem işareti ise :
i.	yığının en üstünde sol parantez varsa veya en üstteki işaretin önceliği gelen işaretten düşük ise işlem işareti yığına  push edilir. 
ii.	
ii. Gelenişaretin önceliğien üstteki işaretin önceliğinden daha düşük ise yığındaki gelenişaretten yüksek öncelikli bütün işaretler için  pop işlemi yapılır.  
iii. Stackten pop edilen işaretler postfix ifadeye eklenir. 
iv. İşlem işareti  yığına  push edilir. 
 ifadeler bittiğinde :yığındaki işaretler sıra ile pop  edilerek postfix ifadeye eklenir. 


 Postfix İfadenin Çözülmesi : 

İlk aşamanın sonunda elde edilen postfix ifadeyi yığın  veri yapısı kullanarak çözen  işlemi yapan fonkisyonu yazilacak
İşlem Adımları : 
Postfix ifade soldan saga doğru değerlendirilir. 
Eğer o anda bakılan karakter: 

 sayı  ise :sayı  yığına  push edilir.
 değişken ise : değişkenin değeri yığına  push edilir.
 işlem işareti ise: yığının üstündeki iki değer pop edilerek  aralarında bu işlem yapılır. İşlem sonucu yığının en üstüne yerleştirilir. 


UYGULAMA
Örnek:
Giriş : c = a *( b +4)  ;

İşlemler: a değişken olduğu için postfix’e eklenir: 
Postfix : a                  Yığın : Boş
* yığına push edilir: 
Postfix : a                   Yığın :  *
 (  yığına push edilir:
Postfix : a                  Yığın :  * (
B değişken olduğu için postfix’e eklenir: 
Postfix : a b               Yığın :  * (
+ yığının en üstünde ( olduğu için yığına push edilir:
Postfix : a b               Yığın :  * (  +
4 sayı olduğu için postfix’e eklenir: 
Postfix : a b 4             Yığın :   * (  +
) geldiği için (‘e kadar olan işaretler yığından pop edilip postfix’e eklenir.
 ( işareti pop Edilir ama postfix’e eklenmez. 
Postfix : a b 4 + *        Yığın :   Boş
; işareti aritmetik ifadenin bittiğini gösterir. 
 Bu durumda eğer yığında hala eleman var ise sıra ile 
pop edilip postfix’e eklenmelidir.
 
Ara Çıkış : a b 4 + *
ve a 2  , b 3 için aritmetik ifade aşağıdaki gibi çözülür:

İşlemler:
A değişken olduğu için sayı değeri yığına push edilir:
Yığın : 2
B değişken olduğu için sayı değeri yığına push edilir:
Yığın :  23
4 sayı olduğu için yığına push edilir:
Yığın :  2 3 4 
+ işlem işareti olduğu için yığının en üstündeki iki sayı pop edilir. Aralarında toplama  işlemi yapılır.
Toplam sonucu yığına push edilir.  
Yığın :  2 7
 *  işlem işareti olduğu için yığının en üstündeki iki sayı pop edilir. Aralarında çarpma  işlemi yapılır.
İşlem sonucu yığına push edilir.  
Yığın :  14
Postfix ifade bittiği için yığındaki sayı pop edilir. Bu sayıc değişkeninin yeni değeri olur.

Sonuc :
Stack yapisi yardimiyla postfix formuna  donusturmek gibi algoritmalar cozulmesi daha kolay hale gelir .
Bir matematiksel ifade cozmek icin postfix formu kullanmak daha kolay olur ,cunku postfixte islem sirasi ve onceliginin kalkmis olur.

Not : Cozum ve uygulama kisminda VeriYapilariOdev5.pdf dosyasindan yararlandi.



 

