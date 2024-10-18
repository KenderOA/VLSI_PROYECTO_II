# VLSI_PROYECTO_II

### Parte 1. Estimación de retardo y consumo promedio de potencia

Diseñar un circuito CMOS estático para calcular $F=(A+B)(C+D)$ con el menor retardo posible. Cada entrada puede tener un máximo de de 30$\lambda$ de ancho de transistor. La salida debe manejar una carga equivalente a 500$\lambda$ de ancho de transistor. Seleccionar tamaños de transistores para lograr el menor retardo posible.

**Compuerta con etapas simples**

Para la estimación del retardo de la compuerta compleja se realizaron los cálculos basados en la teoría de esfuerzo lógico.

![](https://documents.lucid.app/documents/8c1695a0-176d-422f-902b-6a6f997d5b2a/pages/0_0?a=338&x=-155&y=297&w=671&h=407&store=1&accept=image%2F*&auth=LCA%20c26308a973d661005aee367592440b6e8e908195442417bd66aa59fe30746d94-ts%3D1729217234)

**Esfuerzo Eléctrico (fanout)** $$H=\frac{C_{out(path)}}{C_{in(path)}}=\frac{500}{30}=\frac{50}{3}$$
**Esfuerzo por ramificación**
$$B=1$$
**Esfuerzo lógico**
$$G=g_{or} \cdot g_{and} = \frac{5}{3} \cdot \frac{5}{3} = \frac{25}{9}$$
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
