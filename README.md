<h1>Проектна задача по предметот Визуелно програмирање</h1>
<h2>Jigsaw Puzzle</h2></br>
<h3>Опис на проектот</h3></hr>
<p>Сите ние како помали се имаме играно со сложувалки, претежно од со слика на некој од хероите од цртаните филмови. Jigsaw Puzzle е едноставна имплементација на оваа игра на компјутер  во која главната цел е да се состави претходно поделена слика на мали парчиња. Играта има 3 начини на играње лесно, средно и тешко. 
Исто така, за време на играњето постои опција за повремено покажување на помош – односно сликата која ја составуваме да ни се прикаже избледена во позадина.
Постои и опција за рестартирање на играта.
</p>
<h3>Почетен поглед на игратa</h3>
<p>Почетниот поглед на играта се состои од 5 копчиња, слика и кратко упатство за играње на играта.
Со играње може да се почне на три начини:
<ul type="square">
	<li>Со избирање на една од веќе дадените слики</li>
	<li>Со отворање на слика која сакаме да ја сложуваме</li>
	<li>Со drag and drop на некоја слика над формата</li>
</ul>
</p>
<img src="https://cloud.githubusercontent.com/assets/7547420/2938469/0ab088fa-d90d-11e3-8822-9d0c8de3b483.png">
<p>На копчето – Select puzzle – се отвора нова форма од која може да избереме слика за игра.<br>
На копчето – Atach your picture –  се отвара file Dialog прозорец со што може да избереме наша слика за играње.<br>
На копчето означено со знаменце ( surrender ) – ја рестартираме играта.<br> 
Следно е копчето Mode, со клик на ова копче го менуваме начинот на игра во лесно, средно или тешко.<br>
</p>
<img src="https://cloud.githubusercontent.com/assets/7547420/2938470/0d858954-d90d-11e3-9e31-d498ce2f401c.png">
<p>Hide Hint Image или Show Hint Image се користи за време на играње на играта и со ова својство се прикажува / брише замаглената слика од позадина.</p><br>
<h2>Избирање на слика за играње</h2>
<img src="https://cloud.githubusercontent.com/assets/7547420/2938471/0f4c29a0-d90d-11e3-9ef1-dd6cb7c35c69.png" align="center">
<p>Со клкинување врз – Select your game – се отвора нова форма во која има 10 слики.<br> 
Во оваа форма има објаснување како да се избере слика, односо со кликнување врз една од сликите се избира истата и се почнува со играње.</p>
<h2>Избирање ниво на игра</h2>
<p>Играта може да се игра на лесно, средно и тешко ниво.</p>
 <p>Во зависност од одбраното ниво на игра,сликата се дели на повеќе еднакви делчиња. Исто така од нивото на играта зависат уште два параметри тоа се snapDistance и snapDifference кои одредуваат на која одалеченост  ќе се спојат две делчиња при нивно доближување. </p>
<img src="https://cloud.githubusercontent.com/assets/7547420/2938472/107fc890-d90d-11e3-9a47-478152d6f54c.png" align="center">
<p>Моја препорка е на easy да се игра, најлесно е :D .</p>
<h2>Играње</h2>
<p>Основната логика на играта е добро позната : состави ги сите делчиња за да победиш.</p>
<img src="https://cloud.githubusercontent.com/assets/7547420/2938473/11dfa16a-d90d-11e3-9bea-6029a30bdce0.png">
<p>Делчињата немора да се наместат директно врз сликата која стои во позадина, односно да имаат фиксна позиција, туку може да се составуваат било каде на површината. <p>
<img src="https://cloud.githubusercontent.com/assets/7547420/2938474/1692dcd6-d90d-11e3-99e6-d8416058049b.png">
<p>Откако ќе се состави сложувалката, се додека играчот не почне нова игра, сложената слика останува на површината со што може играчот може уште да си ја движи чувствувајќи се гордо што успеал да ја состави :P .</p>
<h2>Класи и логика</h2>
<p>
Играта е составена од вкупно 6 класи и 2 форми.<br>  
Game – ова е оснновната класа на играта во која што се чуваат сите делчиња и функциите кои ја прават основната логика на играта.<br>
</ul>
<hr>
<p>GameSettings  – Статичка класа во која се чуваат основните својства врз кои се темели играта.Односно, ширина и висина на минималната слика која може да се внесе, ширина и висина на делчињата на играта, на колку растојание да се спојуваат парчињата и слично.<br/>
ImageProcessing – Класа во која се наоѓаат сите функции за обработка на сликите, како на пример намалување на слика, промена на транспарентност и слично. <br/>
Piece – Класа во која се чуваат информации за едно делче од играта, како на пример, позиција, сликата со која е представено истото и слично. <br/>
Cluster – Класа во која се чува листа на делчиња од играта. Потребна зашто кога ќе се спојат две делчиња или повеќе мора да бидат групирани некако. <br/>
Во формата Images се чуваат сликите од кои играчот може да избира со каква слика сака да составува сложувалка.
</p>
<hr>
<p>
Откако ќе се внесе слика,( на било кој начин од горе наведените ), во зависност од нивото на играта ( лесно, средно, тешко ), се поставуваат параметрите ( големина на едно парче, растојание на кое се спојуваат делчињата)  во класага GameSettings. Потоа се креира нова инстанца од класата Game и се креираат инстанци од класите Piece и Cluster. 
</p>
 <p>
 Во настанот mouseMove, прво се проверува дали постои селектирано делче и ако постои, истото цело време се прецртува на новата позиција. Со едноставни математички пресметки се проверува дали истото може да се спои со некое друго делче и од која страна. 
 </p>
 <hr>
 <p>
  
Малку потешко беше средувањето на проблемите од типот на прецртувањето на делчињата на пообемни слики кое во некои случаи работеше бавно. Со соодветен resize на сликите и користење на дополнителен бафер со битмапа, успеавме да ги решиме овие проблеми.
</p>
 <p color="teal" >#enjoy playing </p>
 
