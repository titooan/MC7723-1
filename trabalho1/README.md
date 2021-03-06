# Projet 1 - Parte 3
#####Titouan THIBAUD - RA : 180879

##Introdução

Nesse projeto procuramos entender o que é um benchmark, e desenvolver um benchmark usando um programa OpenSource existante.   
O objectivo desse benchmark era comparar o desempenho de varias máquinas, baseado em varios criterios, que tinhamos que escolher. 

Depois do fim da parte 2 do projeto, temos resultados de varios programas de benchmark rodados em varias máquinas diferentes. Vamos usar esses dados para tentar comparar o desempenho das máquinas.

##Avaliação de desempenho

Comparar o tempo de execucção de um mesmo programa em varios computadores já pode dar uma boa ideia do desempenho relativo deles. 
Por exemplo, com o programma `ffmpeg` o computador que demora 14,84s tem um desempenho obviamente melhor que o computador que demora 69,65s.

O benchmark 5 (ordenação) também nos permite comparar o desempenho dos computadores usando o tempo de execução de varios algoritmos de ordenação. 
Podemos ver que os resultados de todos os algoritmos utilizados nos dão a mesmo ordenação dos computadores : computador 4 > computador 22 > computador 15 > computador 20 > computador 11 > computador 17 > computador 31 > computador 23    

Também podemos ver que os resultados de dois computadores de um mesmo modelo tem resultados muito similares com o mesmo programa de benchmark, o que confirma que o benchmark é estavel. (Máquina 9 e Máquina 21 com o benchmark 6 tem resultados muito proximos, e são máquinas com a mesma configuração). 

As Máquinas 6, 7, 15, 24, foram usadas com os 3 programas de benchmark do meu grupo. É interesante ver se os resultados desses 3 benchmarks classificam as máquinas na mesma ordem. Aqui são os tempo de execução dos 3 programas nas 4 Máquinas :  
![resultados](https://github.com/titooan/MC723/blob/master/trabalho1/resultados.png "resultados")  

Só tem resultados estranhos no benchmark 6 da máquina 15 : descobrimos que os resultados foram colocados em ordem errada e que alguns numeros foram tomados do lugar errado no resultado do benchmark também. O resto faz sentido. 

A gente pode também comparar o tempo de leitura para comparar o desempenho dos discos dos computadores. Sem sorpresa, um computador que tem um SSD tem um desempenho muito melhor que um computador que tem um HDD. 
(Exemplo : Máquina 15 vs Máquina 16) 

No caso das máquinas 6, 7, 15, 24, o desempenho do disco nos permite ordenar as máquinas na mesma ordem que o tempo de execução, mas não é nécessariamente ligado : depende do processador, mas também do disco mesmo (tecnologia e tpm). 
Porem, o programa do benchmark 3 escreve e le no disco, então faz sentido que o tempo de execução seja ligado ao desempenho do disco. 

Com os resultados dos benchmarks cheguei a essa ordenação : (alguns resultados se não concordam perfeitamente, mas fiz essa ordenação tentando combinar os resultados dos benchmarks para ter um resultado o mais confiavel possivel)

Máquina 4 ( = Máquina 26) > Máquina 18 > Máquina 10 > Máquina 5 > Máquina 15 > Máquina 7 > Máquina 13 > Máquina 25 > Máquina 12 > Máquina 22 > Máquina 30 > Máquina 3 > Máquina 8 > Máquina 23  

(Máquina 4 : melhor desempenho, Máquina 23 : desempenho pior)

O benchmark 2 nos permite ordenar um outro grupo de máquinas, mas é dificil fazer uma ordenação de todas que seja certa com certeza, porque temos resultados em benchmarks diferentes.  

Máquina 15 > Máquina 14 > Máquina 24 > Máquina 6 > Máquina 16 

Ordenei as máquinas seguinte com os dados do benchmark 8 :  
Máquina 29 > Máquina 7 > Máquina 30 > Máquina 28 > Máquina 11  

Por fim, ordenei essas máquinas com os dados do benchmark 6 que pareciam certos : 
Máquina 9 > Máquina 21 > Máquina 6

###Outras informações analisadas com os dados

Além dos tempos de execução, o benchmark 6 traz algumas outras informações interessantes. 
A frequencia dos ciclos e o numero de instruções por ciclo dam uma ideia das optimizaçoẽs que o processador é capaz de fazer. 

Os dois dám essa ordem :    
Máquina 26 > Máquina 24 > Máquina 7 > Máquina 15 > Máquina  21 >  Máquina  9 > Máquina  17 > Máquina 31   
As máquinas 17, 21 e 9 tem resultados muitos parecidos, o que faz sentido porque são máquina do IC com a mesma configuração.    

O Task-Clock representa o nivel de paralelização médio, e da essa ordem :     
Máquina 7 > Máquina 15 > Máquina 24 > Máquina 17 > Máquina 9  > Máquina 21  > Máquina 31  
Sem sorpresa, as máquinas com configurações mais recentes tem os melhores resultados.

###Conclusão

Os dados obtidos com os diferentes benchmark nos permitiram comparar o desempenho de varias máquinas, baseado em varios criterios. Não consegui fazer uma ordenação incluindo todas as máquinas porque não todas rodaram os mesmos programas de benchmark, mas mesmo assim deu para fazer uma comparação interessante entre varios grupos de maquinas.
