# VLSI_PROYECTO_II

### Parte 1. Estimación de retardo y consumo promedio de potencia

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

$$D=NF^{\frac{1}{N}}+P=2\left(  \frac{100}{3} \right) ^{\frac{1}{2}}+4=16.54$$

**Compuerta con etapas simples**

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

El retardo de la compuerta es de 17.6$\tau$ por lo que la estimación del retardo es
$$D=17.6 \cdot 30.64ps \approx 539.26ps$$

### Parte 2. Determinación de los diferentes tipos de retardo $t_{pdr}, t_{pdf}$ y de contaminación $t_{cdr}, t_{cdf}$

Para el análisis de tiempos de retardo y contaminación se utilizó la aproximación de Elmore y considerando una tecnología de transistores 1.8V (ne,pe) de un proceso de XH018 - 0.18 $\mu$m donde el $\tau_r=21.31ps$ y $\tau_f=30.64ps$ 

**Compuerta con etapas complejas**

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=1383&x=-1268&y=-1740&w=2816&h=1940&store=1&accept=image%2F*&auth=LCA%203998641ca8684ea55756a204436373c3d1891f0c63416695453d5698c47316a1-ts%3D1729280601)

### Parte 3. Diseño de las compuertas y selección de tamaños

**Compuerta con etapas simples**
A continuación se presentan los cálculos y el diseño de la compuerta con tamaños de transistores necesarios

**Esfuerzo de etapa**

$$f̂=F^{\frac{1}{N}}=6.8$$

 **Cálculo del tamaño de los transistores**
 
 $$C_{in_{i}}=\frac{C_{out_i}  \cdot g_i}{f̂}$$
 
  $$C_{in_{2}}=\frac{500\lambda  \cdot \frac{5}{3}}{6.8} \approx 122 \lambda$$

$$C_{in_{1}}=\frac{122\lambda  \cdot \frac{5}{3}}{6.8} \approx 30 \lambda$$
