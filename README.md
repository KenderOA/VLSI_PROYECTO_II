# VLSI_PROYECTO_II

## Parte 1. Estimación de retardo y consumo promedio de potencia

Diseñar un circuito CMOS estático para calcular $F=(A+B)(C+D)$ con el menor retardo posible. Cada entrada puede tener un máximo de de 30 $\lambda$ de ancho de transistor. La salida debe manejar una carga equivalente a 500 $\lambda$ de ancho de transistor. Seleccionar tamaños de transistores para lograr el menor retardo posible.

### Compuerta con etapas complejas

![](https://documents.lucid.app/documents/a1e1e3ec-c96b-4d77-837c-5420ae4eb0e7/pages/0_0?a=1018&x=387&y=262&w=726&h=336&store=1&accept=image%2F*&auth=LCA%20e2c7d780d761c5e0637c1e12472d41f16a62696c3cf9ae93fae47877ce87cf2e-ts%3D1729293097)


Para la estimación del retardo de la compuerta compleja se realizaron los cálculos basados en la teoría de esfuerzo lógico.

**Esfuerzo Eléctrico (fanout)** 

$$H=\frac{C_{out(path)}}{C_{in(path)}}=\frac{500}{30}=\frac{50}{3}$$

**Esfuerzo por ramificación**

$$B=1$$

**Esfuerzo lógico**

$$G=g_{A} \cdot g_{inv} = 2 \cdot 1 = 2$$

**Esfuerzo**

$$F=GBH= 2 \cdot 1 \cdot \frac{50}{3}=\frac{100}{3}$$

**Retardo parasitivo**

$$P=p_{or}+p_{nand}+p_{inv}=2+2+1=5$$

**Número de etapas**

$$N=2$$

**Retardo mínimo**

$$D=NF^{\frac{1}{N}}+P=2\left(  \frac{100}{3} \right) ^{\frac{1}{2}}+5=16.54$$

El retardo de la compuerta es de 16.54$\tau$ por lo que la estimación del retardo considerando el $\tau$ más lento (el peor caso) se utiliza el $\tau_f=30.64ps$, por lo tanto

$$D=16.54 \cdot 30.64ps \approx 506.78ps$$

Con el retardo anterior se determina la frecuencia máxima en la que puede operar la compuerta

$$F_{max}=\frac{1}{506.78ps} \approx 1.97 GHz$$

**Potencia**

$$P_A = P_B = P_C = P_D = 0.25$$

$$P_i = \frac{9}{256}$$

$$ \alpha = \frac{9}{256} \cdot \frac{247}{256} = \frac{2223}{65536}$$

$$C = 450 \tfrac{pf}{(\mu m)^2}$$

$$P_{sw} = \alpha \cdot C \cdot \left(  V_{DD} \right)^2 \cdot f $$

$$P_{sw} = \frac{2223}{65536} \cdot 450 \tfrac{pF}{\mu m^2} \cdot \left(  1.8 \right)^2 \cdot 1.97 GHz = ???$$

### Compuerta con etapas simples

Para la estimación del retardo de la compuerta compleja se realizaron los cálculos basados en la teoría de esfuerzo lógico.

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=338&x=-155&y=297&w=671&h=407&store=1&accept=image%2F*&auth=LCA%20c26308a973d661005aee367592440b6e8e908195442417bd66aa59fe30746d94-ts%3D1729217234)

**Esfuerzo Eléctrico (fanout)**

$$H=\frac{C_{out(path)}}{C_{in(path)}}=\frac{500}{30}=\frac{50}{3}$$

**Esfuerzo por ramificación**

$$B=1$$

**Esfuerzo lógico**

$$G=g_{1} \cdot g_{2} = \frac{5}{3} \cdot \frac{5}{3} = \frac{25}{9}$$

**Esfuerzo**

$$F=GBH= \frac{25}{9} \cdot 1 \cdot \frac{50}{3}=\frac{1250}{27}$$

**Retardo parasitivo**

$$P=p_{or}+p_{and}=2+2=4$$

**Número de etapas**

$$N=2$$

**Retardo mínimo**

$$D=NF^{\frac{1}{N}}+P=2\left(  \frac{1250}{27} \right) ^{\frac{1}{2}}+4=17.6$$

El retardo de la compuerta es de 17.6$\tau$ por lo que la estimación del retardo considerando el $\tau$ más lento (el peor caso) se utiliza el $\tau_f=30.64ps$, por lo tanto

$$D=17.6 \cdot 30.64ps \approx 539.26ps$$

Con el retardo anterior se determina la frecuencia máxima en la que puede operar la compuerta

$$F_{max}=\frac{1}{539.26ps} \approx 1.85 GHz$$

**Potencia**

$$P_A = P_B = P_C = P_D = 0.25$$

$$P_i = \frac{225}{256}$$

$$ \alpha = \frac{225}{256} \cdot \frac{31}{256} = \frac{6975}{65536}$$

$$C = 450 \tfrac{pf}{(\mu m)^2}$$

$$P_{sw} = \alpha \cdot C \cdot \left(  V_{DD} \right)^2 \cdot f $$

$$P_{sw} = \frac{6975}{65536} \cdot 450 \tfrac{pF}{\mu m^2} \cdot \left(  1.8 \right)^2 \cdot 1.85 GHz = $$

## Parte 2. Determinación de los diferentes tipos de retardo $t_{pdr}, t_{pdf}$ y de contaminación $t_{cdr}, t_{cdf}$

Para el análisis de tiempos de retardo y contaminación se utilizó la aproximación de Elmore y considerando una tecnología de transistores 1.8V (ne,pe) de un proceso de XH018 - 0.18 $\mu$m donde el $\tau_r=21.1ps$ y $\tau_f=30.64ps$ 

**Compuerta con etapas complejas**

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=1979&x=-786&y=501&w=1724&h=1113&store=1&accept=image%2F*&auth=LCA%202aabb06375cf194994398b8100d9887fdabf6f4be3754c140b7cd8b8f0cf962c-ts%3D1729561784)

### $t_{pdf}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2060&x=1452&y=-1634&w=616&h=663&store=1&accept=image%2F*&auth=LCA%200eec7f7dac5a7da7dbadf8c104dba492ed4e99b6dd577d87d0d5d0a9fc087fa3-ts%3D1729561784)

$$ \tau_r = RC = 21.1 ps$$
$$ t_{pdf} = 15C \cdot R + 2C \cdot \frac{R}{2}$$
$$t_{pdf} = 16RC = 337.6ps$$

### $t_{cdf}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2072&x=1452&y=-1634&w=616&h=663&store=1&accept=image%2F*&auth=LCA%20c2ebcfdfd6f7bbd3bee60860ba6704ee0a98a03360aaa3e13f6ecc2519344f2e-ts%3D1729561784)

$$ \tau_r = RC = 21.1 ps$$
$$ t_{cdf} = 15C \cdot \left( \frac{R}{4} +\frac{R}{4} \right) + 2C \cdot \frac{R}{4}$$
$$t_{cdf} = 8RC = 168.8ps$$

### $t_{pdr}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2131&x=1456&y=-1576&w=533&h=785&store=1&accept=image%2F*&auth=LCA%20592b4d94bcc77785616bd15eef14f834aa39d0670544e9f576b2d73ff82ecf16-ts%3D1729561784)

$$ \tau_r = RC = 30.64 ps$$
$$ t_{pdr} = 15C \cdot R + 4C \cdot \frac{R}{2}$$
$$t_{pdr} = 17RC = 520.88ps$$

### $t_{cdr}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2143&x=1456&y=-1576&w=533&h=785&store=1&accept=image%2F*&auth=LCA%201f5d0ce0bd7eb4b30f0983b051efee52e3207f6c362fdc0472858003d8b363d6-ts%3D1729561784)

$$ \tau_r = RC = 30.64ps$$
$$ t_{cdr} = 15C \cdot \left( \frac{R}{4} + \frac{R}{4} \right) + 4C \cdot \frac{R}{4}$$
$$t_{cdr} = \frac{17}{2} RC = 260.44ps$$

**Inversor de la compuerta**

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2186&x=1561&y=-2098&w=418&h=400&store=1&accept=image%2F*&auth=LCA%20b68faa3f7b20a36cecded8d505c1dec4889c81159dfcc35b01eab6e8e20e659a-ts%3D1729561784)

$$t_{pdf}=t_{cdf}$$
$$ \tau_r = RC = 21.1 ps$$
$$t_{pdf} = 3RC = 63.3ps$$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2209&x=1475&y=-1557&w=550&h=385&store=1&accept=image%2F*&auth=LCA%20a8ffeef37c02bdfee9bd3843e8b061057e56809f61ac5e9d5c7c185b094453be-ts%3D1729561784)

$$t_{pdr}=t_{cdr}$$
$$ \tau_r = RC = 30.64 ps$$
$$t_{pdr} = 3RC = 91.92ps$$

Para determinar en su totalidad los tiempos de retardo se sumaron los resultados, de manera que:

| $t_{pdf}$ | Column 2 |
|----------|----------|
| $t_{cdf}$  | Cell 2   | 
| $t_{pdr}$   | Cell 5   |
| $t_{cdr}$   | Cell 8   |


**Compuerta con etapas simples**

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3533&x=-1253&y=-1734&w=2486&h=1892&store=1&accept=image%2F*&auth=LCA%20db52691ed77e5ee1803354a8e36c9cb5bea4a18b538292806e33b0ad4f8b4eed-ts%3D1729897525)

### $t_{pdf}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3195&x=1560&y=-2098&w=440&h=400&store=1&accept=image%2F*&auth=LCA%2010b8f017d8236312fedcf5342709fd9e7cd4cbe7b6bcfb3dc7299f1c23222b9b-ts%3D1729716047)

$$ \tau_r = RC = 21.1ps$$
$$ t_{pdf} = 11RC = 232.1ps$$

### $t_{cdf}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3210&x=1539&y=-2098&w=462&h=400&store=1&accept=image%2F*&auth=LCA%20375f226ebf1602cbeaec7af0fbd115f381cbb67c12782ae61e082fa6a86d7d07-ts%3D1729716047)

$$ \tau_r = RC = 21.1ps$$
$$ t_{cdf} = \frac{11}{2}RC = 116.05ps$$

### $t_{pdr} = t_{cdr}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3304&x=1454&y=-1571&w=572&h=692&store=1&accept=image%2F*&auth=LCA%20dadf025c6af4fe28ca745d09f9bc0f5627f3156cfa4804b3f8964afa2e42abc2-ts%3D1729897525)

$$ \tau_r = RC = 30.64ps$$
$$ t_{pdr} = t_{cdr} = 11C \cdot \left( \frac{R}{2} + \frac{R}{2} \right) + 4C \cdot \frac{R}{2}$$
$$t_{pdr} = t_{cdr} = 13 RC = 398.32ps$$

Para la segunda compuerta NOR

### $t_{pdf}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3347&x=1561&y=-2098&w=418&h=400&store=1&accept=image%2F*&auth=LCA%208204ab962894823d03952de7cfbb864909d950f5274b5233d71fc35aec3bde84-ts%3D1729897525)

$$ \tau_r = RC = 21.1ps$$
$$ t_{pdf} = 6RC = 126.6ps$$

### $t_{cdf}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3361&x=1540&y=-2098&w=440&h=400&store=1&accept=image%2F*&auth=LCA%2088f8900e0e812b4a30f8904dd15f456ac2afe8e5014bcdbf25c289167c8f569f-ts%3D1729897525)

$$ \tau_r = RC = 21.1ps$$
$$ t_{cdf} = 3RC = 63.3ps$$

### $t_{pdr} = t_{cdr}$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3317&x=1455&y=-1571&w=555&h=685&store=1&accept=image%2F*&auth=LCA%20e261de4111192123a9991e196abfd9110d3effb79015cac8b79b1c00aaa22cde-ts%3D1729897525)

$$ \tau_r = RC = 30.64ps$$
$$ t_{pdr} = t_{cdr} = 6C \cdot \left( \frac{R}{2} + \frac{R}{2} \right) + 4C \cdot \frac{R}{2}$$
$$t_{pdr} = t_{cdr} = 8 RC = 245.12ps$$

Para determinar en su totalidad los tiempos de retardo se sumaron los resultados, de manera que:

|  | Delay (ps)|
|----------|----------|
| $t_{pdf}$ | 524.92|
| $t_{cdf}$  | 461.62  | 
| $t_{pdr}$   | 477.22 |
| $t_{cdr}$   | 361.17 |

## Parte 3. Diseño de las compuertas y selección de tamaños

**Compuerta con etapas complejas**

A continuación se presentan los cálculos y el diseño de la compuerta con tamaños de transistores necesarios

**Esfuerzo de etapa**

$$f̂=F^{\frac{1}{N}}=5.77$$

 **Cálculo del tamaño de los transistores**
 
 $$C_{in_{i}}=\frac{C_{out_i}  \cdot g_i}{f̂}$$
 
  $$C_{in_{2}}=\frac{500\lambda  \cdot \frac{5}{3}}{5.77} \approx 86 \lambda$$

$$C_{in_{1}}=\frac{86 \lambda  \cdot \frac{5}{3}}{5.77} \approx 30 \lambda$$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2307&x=-786&y=501&w=1724&h=1113&store=1&accept=image%2F*&auth=LCA%203f029a6ea3b7244d4f5ec03ec0f9503aa043ba2e076b8c4dbf58aa8e808d4754-ts%3D1729561784)

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=3145&x=-4540&y=-3138&w=657&h=343&store=1&accept=image%2F*&auth=LCA%2063d322439f0e161ad8e493f13f3fbcf2ee62cbabd8aa3144366120b0be8c5090-ts%3D1729645144)

**Compuerta con etapas simples**

A continuación se presentan los cálculos y el diseño de la compuerta con tamaños de transistores necesarios

**Esfuerzo de etapa**

$$f̂=F^{\frac{1}{N}}=6.8$$

 **Cálculo del tamaño de los transistores**
 
 $$C_{in_{i}}=\frac{C_{out_i}  \cdot g_i}{f̂}$$
 
  $$C_{in_{2}}=\frac{500\lambda  \cdot \frac{5}{3}}{6.8} \approx 122 \lambda$$

$$C_{in_{1}}=\frac{122 \lambda  \cdot \frac{5}{3}}{6.8} \approx 30 \lambda$$

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=2669&x=-1253&y=-1734&w=2486&h=1892&store=1&accept=image%2F*&auth=LCA%20c9763dd3c104b6840919c180546aafd4c41522a1db1564baea668c2e28df9910-ts%3D1729561784)
## Parte 4. Diseño trazado

**Esquemático  de la circuito simple**
![image](https://github.com/user-attachments/assets/66355b32-c70a-4ea9-b136-acf4b0fb97f2)

**Layout de la circuito primeras 2 compuertas or**

![image](https://github.com/user-attachments/assets/b8ac7c6c-c20d-4136-a96d-3bebb8767811)

**Layout de la circuito última compuerta or**
![image](https://github.com/user-attachments/assets/b7c44624-6e6d-4e7b-8eea-9218e05734a1)

**Simulación de la circuito simple**
![image](https://github.com/user-attachments/assets/ae7f04ff-601c-4a5a-b50e-4e02b7dded1a)

**Esquemático de la circuito OAI**
![image](https://github.com/user-attachments/assets/73921ee8-79f3-4435-adf6-36746b38f014)

**Layout de la primera parte del circuito OAI**
![image](https://github.com/user-attachments/assets/839d839a-5640-45d3-be5d-aed03081bd02)

**Layout del inversor del circuito OAI**
![image](https://github.com/user-attachments/assets/d5bd63d6-b248-407f-8974-7cd7a75dcde5)

**Simulación de la circuito OAI**
![image](https://github.com/user-attachments/assets/be6d3d99-1fdf-4b56-95c7-eedf8e996694)
