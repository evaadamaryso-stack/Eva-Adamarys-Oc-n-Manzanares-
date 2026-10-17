import java.util.Scanner;

public class factorizarMatriz {


    static Scanner sc = new Scanner(System.in);

    static double pedirNumero(String mensaje) {
        while (true) {
            System.out.print(mensaje);
            String texto = sc.nextLine().trim();

            try {

                if (texto.contains("/")) {
                    String[] partes = texto.split("/");
                    double arriba = Double.parseDouble(partes[0].trim());
                    double abajo  = Double.parseDouble(partes[1].trim());

                    if (abajo == 0) {
                        System.out.println("El denominador no puede ser cero.");
                        continue;
                    }
                    return arriba / abajo;
                }

                else {
                    return Double.parseDouble(texto);
                }
            } catch (Exception e) {
                System.out.println("Dato incorrecto. Ejemplos: 5, 2.5, 3/4");
            }
        }
    }


    static void mostrarMatriz(String nombre, double[][] m) {
        System.out.println();
        System.out.println(nombre);
        for (int i = 0; i < 3; i++) {
            System.out.print("[ ");
            for (int j = 0; j < 3; j++) {
                System.out.print(m[i][j] + " ");
            }
            System.out.println("]");
        }
    }


    public static void main(String[] args) {

        System.out.println("======================================");
        System.out.println("   FACTORIZACIÓN LU DE UNA MATRIZ 3x3");
        System.out.println("           MÉTODO DE DOOLITTLE");
        System.out.println("======================================");
        System.out.println();
        System.out.println("Ejemplos válidos: 5, 2.5, 3/4, -7/3");
        System.out.println();

        System.out.println("INGRESE LOS ELEMENTOS DE LA MATRIZ A");
        System.out.println("--------------------------------------");

        double[][] A = new double[3][3];

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                A[i][j] = pedirNumero("Ingrese a" + (i + 1) + (j + 1) + ": ");
            }
        }

        double[][] L = new double[3][3];
        double[][] U = new double[3][3];

        L[0][0] = 1;
        L[1][1] = 1;
        L[2][2] = 1;




        U[0][0] = A[0][0];
        U[0][1] = A[0][1];
        U[0][2] = A[0][2];


        if (U[0][0] == 0) {
            System.out.println();
            System.out.println("No se puede factorizar: el primer pivote es cero.");
            return;
        }


        L[1][0] = A[1][0] / U[0][0];
        L[2][0] = A[2][0] / U[0][0];

        U[1][1] = A[1][1] - L[1][0] * U[0][1];
        U[1][2] = A[1][2] - L[1][0] * U[0][2];


        if (U[1][1] == 0) {
            System.out.println();
            System.out.println("No se puede factorizar: el segundo pivote es cero.");
            return;
        }

        L[2][1] = (A[2][1] - L[2][0] * U[0][1]) / U[1][1];

        U[2][2] = A[2][2]
                - L[2][0] * U[0][2]
                - L[2][1] * U[1][2];


        mostrarMatriz("MATRIZ A:", A);
        mostrarMatriz("MATRIZ L:", L);
        mostrarMatriz("MATRIZ U:", U);

        System.out.println();
        System.out.println("======================================");
        System.out.println("FACTORIZACIÓN:");
        System.out.println("A = L x U");
        System.out.println("======================================");

        sc.close();
    }
}