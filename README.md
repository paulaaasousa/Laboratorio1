# Laboratorio1/pratica1 Micro
Paula Adriana Alves Sousa - 1947923

->> Para esta primeira prática utilizamos na parte A o MOV e mais alguns comandos utilizados em Assembly para manipular números e registradores, como mostrados a seguir:

Iniciamos o registrador R0 com o valor 0x55, utilizando o simbolo #:

MOV R0, #0x55 -> Saída: 0x0000'0055

Em seguida, o registrador R1 receberá o valor contido em R0 deslocado à esquerda (<-) em 16 bits (comando LSL -> deslocamento a esquerda, #16 -> número de bits deslocados).

MOV R1, R0, LSL #16 -> Saída: 0x0055'0000

O Registrador R2 recebe o R1 deslocado 8 bits a direita (->),  (comando LSR -> deslocamento a direita, #8 -> número de bits deslocados).

MOV R2, R1, LSR #8 -> Saída: 0x0000'5500 

R3 recebe R2 após um shift aritmetico de 4 bits para a direita (->), (comando ASR -> shift aritmetico a direita, #4 -> número de bits deslocados).

MOV R3, R2, ASR #4 -> Saída:0x0000'0550

R4 recebe R3 após uma rotação de 2 bits para a direita, (comando ROR -> rotação a direita, #2 -> número de bits rotacionados).

MOV R4, R3, ROR #2 -> Saída: 0x0000'0154

R5 recebe R4 após uma rotação com extensão de 1 bit para a direita, (comando RRX -> rotação a direita com extensão).

MOV R5, R4, RRX -> Saída: 0x0000'00aa

->> Na segunda etapa trocamos o comando MOV para o comando MVN, que tem como funcionalidade negar bit a bit os valores, portanto: 

#0x55 NEGADO:
MVN R0, #0x55 -> Saída: 0xffff'ffaa

Em seguida, o registrador R1 receberá o valor contido em R0 NEGADO deslocado à esquerda (<-) em 16 bits (comando LSL -> deslocamento a esquerda, #16 -> número de bits deslocados).

MVN R1, R0, LSL #16 -> Saída: 0x0055'ffff

O Registrador R2 recebe o R1 NEGADO deslocado 8 bits a direita (->),  (comando LSR -> deslocamento a direita, #8 -> número de bits deslocados).

MVN R2, R1, LSR #8 -> Saída: 0xffff'aa00

R3 recebe R2 NEGADO após um shift aritmetico de 4 bits para a direita (->), (comando ASR -> shift aritmetico a direita, #4 -> número de bits deslocados).

MVN R3, R2, ASR #4 -> Saída: 0x0000'055f

R4 recebe R3 NEGADO após uma rotação de 2 bits para a direita, (comando ROR -> rotação a direita, #2 -> número de bits rotacionados).

MVN R4, R3, ROR #2 -> Saída: 0x3fff'fea8

R5 recebe R4 NEGADO após uma rotação com extensão de 1 bit para a direita, (comando RRX -> rotação a direita com extensão).

MVN R5, R4, RRX -> Saída:0xe000'00ab

Isto tudo foi possível observar na aba View -> Registers -> Registers 1, onde podemos acompanhar junto ao debug do projeto as mudanças nos endereços de memória. Ali podemos ver as informações contidas nos registradores PC, Prismask, SP, LR, APSR, entre outros, bem como suas flags. O PC é responsável por apontar o endereço de memória da próxima instrução que será executada.
