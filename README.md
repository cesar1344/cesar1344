<h1 align="center">¡Hola, soy Cesar! 👋</h1>
<h3 align="center">Estudiante | Aprendiendo Java 🚀</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Estudiante-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Aprendiendo-POO-green?style=for-the-badge" />
</p>

---


Componentes JAVA METODOS. 

(1.) Qué son los pilares (POO) 

Los 4 pilares de la programación orientada a objetos (POO) son los principios fundamentales sonre en los que se construye este paradigma. 

- Encapsulamiento: Consiste en ocultar los datos internos de una clase y controla como se accede a ellos, generalmente usando atributos (PRIVATE) y métodos públicos (GET/ SET) para acceder o modificarlos.  



- Ejemplo. 

class Cuenta {
    private double saldo; // nadie puede tocarlo directamente

    public double getSaldo() {
        return saldo;
    }

    public void depositar(double monto) {
        if (monto > 0) {
            saldo += monto;  
        }


- Idea clave: Protege los datos para que no se puedan cambiar de cualquier forma, solo  a través de métodos, controlados. 

(2.) Herencia. 

- Permite que una clase (hija) obtenga atributos y métodos de otra clase (padre), usando (Extends.) evita repetir códigos. 


- Ejemplo. 

class Animal {
    void comer() { System.out.println("Comiendo..."); }
}

class Perro extends Animal {
    void ladrar() { System.out.println("Guau!"); }
}

- Palabra clave "es un tipo de" - (perro) es un (animal), así que hereda lo que ya tiene. 



(3.) Polimorfismo. 

- Significa "muchas formas". Permite que un mismo método se comporte diferente según la clase que lo use, generalmente sobrescribiendo (@Override) métodos heredados. 


-EJEMPLO. 


java
class Animal {
    void hacerSonido() { System.out.println("Sonido genérico"); }
}

class Gato extends Animal {
    @Override
    void hacerSonido() { System.out.println("Miau"); }
}

class Perro extends Animal {
    @Override
    void hacerSonido() { System.out.println("Guau"); }
}


 Idea clave
 - Puedes tratar a un (GATO) y aun (PERRO) como un (ANIMAL), pero cada uno responde a su manera al mismo método. 



 - (4.) Abstracción. 

 - Consiste en mostrar solo lo esencial de un objeto y ocultar los detalles complejos de implementación. Se logra con clases abstractas o interfaces. 

 - EJEMPLO . 


 abstract class Figura {
    abstract double calcularArea(); // no dice cómo, solo que debe existir
}

class Circulo extends Figura {
    double radio;

    double calcularArea() {
        return Math.PI * radio * radio;
    }
}

- Idea clave: Defines que debes hacer algo, sin preocuparte de cómo lo hace cada clase especifica por dentro. 

-En resumen (con tu ejemplo de la venta):

-Pilar	En tu programa
Encapsulamiento	Si pusieras (private) a (precio) y (cantidad), y solo accedieras con métodos
Herencia	Si crearas (VentaConDescuento) (extends Venta)
Polimorfismo	Si (Venta) y (VentaConDescuento) calcularan el total de forma diferente con el mismo método
Abstracción	Si solo mostraras (mostrarDetalle) sin que el usuario necesite saber cómo se calcula el total por dentro.

(Tema-encapsulamiento)

. El encapsulamiento en Java es el pilar de la (POO) que consiste en ocultar los datos internos de una clase y protegerlos, permitiendo el acceso solo de métodos controlados (generalmente llamados GETTERS Y SETTERS). 

La idea principal
-Es como un capsula de medicina por fuera ves algo simple, pero no puedes tocar directamente lo que hay adentro, solo puedes interactuar con ella de la forma en que está permitida. 

-Cómo se hace el código. 

. Paso 1 : Los atributos se declaran como (Private) nadie de afuera los puede tocar directamente. 

- Ejemplo. 

-class Cuenta {
    private double saldo;
}

. Paso 2 : Se crean métodos públicos para poder leer o modificar ese atributo de forma controlada

- Ejemplo. 

. class Cuenta {
    private double saldo;

    // Getter: para LEER el saldo
    public double getSaldo() {
        return saldo;
    }

    // Setter: para MODIFICAR el saldo, con control
    public void setSaldo(double saldo) {
        if (saldo >= 0) {  // evita que quede en negativo
            this.saldo = saldo;
        }
    }

. Por que sirve esto 
- Sin encapsulamiento, cualquiera podría hacer esto y romper la lógica de tu programa. 

- Ejemplo 

- cuenta.saldo = -5000; // ❌ esto no debería pasar

- Aplicado a tu programa de la venta 
  Ahora mismo tus atributos en la clase (VENTA) están así  (sin encapsular)

  -Ejemplo. 
  
class Venta {
    String cliente;
    double precio;
    int cantidad;
}
  

Con encapsulamiento se vería así.

-Ejemplo. 

-class Venta {
    private String cliente;
    private double precio;
    private int cantidad;

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        if (precio > 0) {  // no permite precios negativos
            this.precio = precio;
        }
    }
}

En resumen: encapsulamiento = private en los atributos + getters/setters públicos para controlar el acceso, protegiendo los datos de cambios indebidos.
        
