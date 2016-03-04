# MC7723-1

**-1**  Podemos especificar as otimizações com as seguintes opções : -O0, -O1, O2,O3

**-2**  Um makefile é um arquivo usado por make, que vai executar as comandas só se elas forem necesarias, ao contrario de um script shell.

**-3** Depurar um programa é usar umas ferramentas para executa-lo passo a passo e conseguir entender e corrigir os problemas que ele tem.

**-4** Podemos usar o gdb com o seguinte comando : ```gdb primo```. O programa tem que ser compilado com a opção ```-g```.

**-5** 

##Atividade

###Otimizações
Tempo de execução com as otimizaões, medido usando ```time ./primo``` :

+ *O0*    
real	0m0.306s  
user	0m0.304s  

+ *O1*  
real	0m0.287s   
user	0m0.285s  

+ *O2*  
real	0m0.345s  
user	0m0.343s  

+ *O3*  
real	0m0.376s  
user	0m0.374s  

**mtune**   
    A opção mtune não se aplica a nosso caso, porque só se aplica a architectura ARM. 
    > This option specifies the name of the target ARM processor for which GCC should tune the performance of the code.

**Arquivos separados**    
Podemos compilar o programa com o script seguinte : 
```gcc -o primo main.c calc_primo.c```

Também pode escrever um makefile assim :    
```
primo: main.c calc_primo.c
gcc -o primo main.c calc_primo.c
```
Nesse caso so precisa rodar "make" para compilar o programa.

O programa gasta um tempo igual para ser excutado. A gente podia prever esse resultado : separar os arquivos só deixa mais facil para o programador organizar seu projeito, mas o compilador vai gerar o mesmo binario depois. 

**Modificação para entrar n como parametro**
So precisa usar esse codigo : 
```
int main(int argc, char** argv)
{
  long n = strtol(argv[1], NULL, 0);
  ...
  ```

Usando o mesmo numero que antes como entrada (104395301), o tempo de execução é esse :
real	0m0.334s
user	0m0.334s

O tempo que eu medi era o mesmo com um ou dois arquivos.
Quase não mudou o tempo de execução em relação a antes, porque o que demora não é analisar o parametro entrado na linha de comando, mas o laço que verifica se o numero é primo ou não.


**Modificação do laço**   
O programa fica bem mais rapido com essa modificação :  
  real	0m0.135s  
  user	0m0.135s  

**




