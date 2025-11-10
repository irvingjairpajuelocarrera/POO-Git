# Proyecto POO-Git
package caso1;
import java.util.Scanner;

public class UsuarioSimple {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("=== Registro de Usuario ===");
        System.out.print("Ingrese su nombre: ");
        String nombre = sc.nextLine();

        System.out.print("Ingrese su edad: ");
        int edad = sc.nextInt();

        System.out.print("Ingrese su altura en metros: ");
        double altura = sc.nextDouble();

        System.out.println("\n--- Datos Registrados ---");
        System.out.println("Nombre: " + nombre);
        System.out.println("Edad: " + edad + " años");
        System.out.println("Altura: " + altura + " m");

        sc.close();
    }
}

     CASO 2: Clase Estudiante con atributos privados

package caso2;
import java.util.Scanner;

class Estudiante {
    private String nombre;
    private int edad;
    private double promedio;

    // Constructor
    public Estudiante(String nombre, int edad, double promedio) {
        this.nombre = nombre;
        this.edad = edad;
        this.promedio = promedio;
    }

    // Métodos Get y Set
    public String getNombre() { return nombre; }
    public void setNombre(String nombre) { this.nombre = nombre; }

    public int getEdad() { return edad; }
    public void setEdad(int edad) { this.edad = edad; }

    public double getPromedio() { return promedio; }
    public void setPromedio(double promedio) { this.promedio = promedio; }

    // Método para mostrar datos
    public void mostrarDatos() {
        System.out.println("\n--- Datos del Estudiante ---");
        System.out.println("Nombre: " + nombre);
        System.out.println("Edad: " + edad + " años");
        System.out.println("Promedio: " + promedio);
    }
}

public class EstudianteInteractivo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Ingrese el nombre del estudiante: ");
        String nombre = sc.nextLine();

        System.out.print("Ingrese la edad: ");
        int edad = sc.nextInt();

        System.out.print("Ingrese el promedio: ");
        double promedio = sc.nextDouble();

        Estudiante est = new Estudiante(nombre, edad, promedio);
        est.mostrarDatos();

        sc.close();
    }
}
CASO 3: Clase CuentaBancaria con validación
package caso3;
import java.util.Scanner;

class CuentaBancaria {
    private String titular;
    private double saldo;

    public CuentaBancaria(String titular, double saldoInicial) {
        this.titular = titular;
        this.saldo = saldoInicial;
    }

    public void depositar(double monto) {
        if (monto > 0) {
            saldo += monto;
            System.out.println("Depósito exitoso. Saldo actual: S/ " + saldo);
        } else {
            System.out.println("El monto debe ser positivo.");
        }
    }

    public void retirar(double monto) {
        if (monto <= 0) {
            System.out.println("Monto inválido.");
        } else if (monto > saldo) {
            System.out.println("Fondos insuficientes. Saldo actual: S/ " + saldo);
        } else {
            saldo -= monto;
            System.out.println("Retiro exitoso. Saldo restante: S/ " + saldo);
        }
    }

    public void mostrarSaldo() {
        System.out.println("Titular: " + titular + " | Saldo actual: S/ " + saldo);
    }
}

public class CuentaBancariaTest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("=== Sistema Bancario ===");
        System.out.print("Ingrese el nombre del titular: ");
        String nombre = sc.nextLine();

        System.out.print("Ingrese el saldo inicial: ");
        double saldoInicial = sc.nextDouble();

        CuentaBancaria cuenta = new CuentaBancaria(nombre, saldoInicial);

        int opcion;
        do {
            System.out.println("\n1. Depositar");
            System.out.println("2. Retirar");
            System.out.println("3. Consultar saldo");
            System.out.println("4. Salir");
            System.out.print("Seleccione una opción: ");
            opcion = sc.nextInt();

            switch (opcion) {
                case 1:
                    System.out.print("Monto a depositar: ");
                    double dep = sc.nextDouble();
                    cuenta.depositar(dep);
                    break;
                case 2:
                    System.out.print("Monto a retirar: ");
                    double ret = sc.nextDouble();
                    cuenta.retirar(ret);
                    break;
                case 3:
                    cuenta.mostrarSaldo();
                    break;
                case 4:
                    System.out.println("Gracias por usar el sistema.");
                    break;
                default:
                    System.out.println("Opción inválida.");
            }
        } while (opcion != 4);

        sc.close();
    }
}










     

        sc.close();
    }
}
