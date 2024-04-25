# Projeto_2

<nta>
<declaration>// Place global declarations here. broadcast chan estado1, estado2, estado3; clock time; int x; const int verde = 32; const int amarelo = 3; const int vermelho = 18; int [0,1] s; //0 é verde, 1 é vermelho </declaration>
<template>
<name>Timer</name>
<declaration>clock y;</declaration>
<location id="id0" x="-1530" y="-433"> </location>
<location id="id1" x="-1317" y="-433"> </location>
<location id="id2" x="-1122" y="-433"> </location>
<init ref="id0"/>
<transition id="id3">
<source ref="id2"/>
<target ref="id0"/>
<label kind="guard" x="-1299" y="-412">y >= vermelho</label>
<label kind="synchronisation" x="-1299" y="-395">estado3 !</label>
<nail x="-1317" y="-323"/>
</transition>
<transition id="id4">
<source ref="id1"/>
<target ref="id2"/>
<label kind="guard" x="-1299" y="-467">y >= amarelo</label>
<label kind="synchronisation" x="-1299" y="-450">estado2 !</label>
</transition>
<transition id="id5">
<source ref="id0"/>
<target ref="id1"/>
<label kind="guard" x="-1512" y="-467">y >= verde</label>
<label kind="synchronisation" x="-1512" y="-450">estado1 !</label>
</transition>
</template>
<template>
<name>Carro</name>
<declaration>clock y; const int d1 = 108; const int d2 = 12; //11.7; const int d3 = 15; //14.4; const int d4 = 16; //15.3; const int d5 = 9; //8.1;</declaration>
<location id="id6" x="-969" y="-195">
<name x="-979" y="-229">Inicio</name>
</location>
<location id="id7" x="-663" y="-195">
<name x="-714" y="-229">Passou_do_Sem1</name>
</location>
<location id="id8" x="-382" y="-195">
<name x="-441" y="-229">Passou_do_Sem2</name>
</location>
<location id="id9" x="552" y="-195">
<name x="542" y="-229">Fim</name>
</location>
<location id="id10" x="238" y="-195">
<name x="179" y="-229">Passou_do_Sem4</name>
</location>
<location id="id11" x="-76" y="-195">
<name x="-127" y="-229">Passou_do_Sem3</name>
</location>
<init ref="id6"/>
<transition id="id12">
<source ref="id11"/>
<target ref="id10"/>
<label kind="guard" x="17" y="-221">s == 0 && y >= d4 && x == 12</label>
<label kind="assignment" x="-58" y="-195">y = 0</label>
</transition>
<transition id="id13">
<source ref="id8"/>
<target ref="id11"/>
<label kind="guard" x="-280" y="-221">s == 0 && y >= d3</label>
<label kind="assignment" x="-364" y="-195">y = 0</label>
</transition>
<transition id="id14">
<source ref="id10"/>
<target ref="id9"/>
<label kind="guard" x="331" y="-221">s == 0 && y >= d5</label>
<label kind="assignment" x="256" y="-195">y = 0</label>
</transition>
<transition id="id15">
<source ref="id7"/>
<target ref="id8"/>
<label kind="guard" x="-595" y="-221">s == 0 && y >= d2</label>
<label kind="assignment" x="-645" y="-195">y = 0</label>
</transition>
<transition id="id16">
<source ref="id6"/>
<target ref="id7"/>
<label kind="guard" x="-901" y="-221">y >= d1 && x == 2*4</label>
<label kind="assignment" x="-798" y="-195">y = 0</label>
</transition>
</template>
<template>
<name x="5" y="5">Semaforo</name>
<declaration>// Place local declarations here. clock y; </declaration>
<location id="id17" x="-1649" y="-569" color="#00ff00">
<name x="-1659" y="-603">Verde</name>
</location>
<location id="id18" x="-1462" y="-569" color="#ffff00">
<name x="-1472" y="-603">Amarelo</name>
</location>
<location id="id19" x="-1292" y="-569" color="#ff0000">
<name x="-1302" y="-603">Vermelho</name>
</location>
<init ref="id17"/>
<transition id="id20">
<source ref="id19"/>
<target ref="id17"/>
<label kind="guard" x="-1487" y="-493">y>=vermelho</label>
<label kind="synchronisation" x="-1479" y="-518">estado3 ?</label>
<label kind="assignment" x="-1470" y="-459">s=0, y = 0, x+=1</label>
<nail x="-1385" y="-467"/>
<nail x="-1453" y="-467"/>
<nail x="-1555" y="-467"/>
</transition>
<transition id="id21">
<source ref="id18"/>
<target ref="id19"/>
<label kind="guard" x="-1419" y="-595">y>=amarelo</label>
<label kind="synchronisation" x="-1402" y="-620">estado2 ?</label>
<label kind="assignment" x="-1402" y="-569">s = 1, y = 0</label>
<nail x="-1368" y="-569"/>
</transition>
<transition id="id22">
<source ref="id17"/>
<target ref="id18"/>
<label kind="guard" x="-1631" y="-603">y >= verde</label>
<label kind="synchronisation" x="-1598" y="-620">estado1 ?</label>
<label kind="assignment" x="-1631" y="-569">y = 0</label>
</transition>
</template>
<system>// Place template instantiations here. car = Carro(); sem_1 = Semaforo(); sem_2 = Semaforo(); sem_3 = Semaforo(); sem_4 = Semaforo(); tes = Timer(); // List one or more processes to be composed into a system. system car,sem_1, sem_2, sem_3, sem_4, tes; </system>
<queries>
<query>
<formula/>
<comment/>
</query>
</queries>
</nta>
