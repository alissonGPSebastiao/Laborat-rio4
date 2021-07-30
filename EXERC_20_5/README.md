\*\*Dentro do código disponibilizado pelo professor, fiz as seguintes alterações\*\*

Na interrupção GPIOJ_Handler adicionei:

LDR R0, [R1, #GPIO_RIS]

Para registrar em R0 o estado do botão. Na quencia adicionei:

cmp R0, #1

para verificar se o Registrador R0 é igual a #1,

Se ele for (ITE EQ), isso faz com que eu adicione (ADDEQ R11, R11, #1) #1 em R11,

Caso contrário, subtraio (SUBNE R11, R11, #1) #1 de R11.

Por fim, na Button_int_conf, mudei o:

MOV R2, #00000001b

para: MOV R2, #00000011b.

Assim, leio tanto PJ0 quanto PJ1.
