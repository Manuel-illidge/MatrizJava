# MatrizJava
Ejercicio de matriz con Java

//Manuel Illidge R.

package modelacion;

import java.io.*;


public class matriz {

    public static void main (String args[]) throws IOException{

        int tam = 2;

        operaciones op = new operaciones();

        int matriz1[][] = new int[tam][tam];  // Datos de la matriz  { {2,0,1},{3,0,0},{5,1,1}};
        int matriz2[][] = new int[tam][tam];  // Datos de la Matriz  { {1,0,1},{1,2,1},{1,1,0}};

        int matriz[][] = new int [tam][tam];

        InputStreamReader isr = new InputStreamReader(System.in);
    	BufferedReader br = new BufferedReader(isr);
        
        System.out.println("ingrese valores de la primera matriz");
        for(int i=0;i<tam;i++){
            for(int j=0;j<tam;j++){
                System.out.println("ingrese valor posicion "+i+"-"+j);
                matriz1[i][j] = Integer.parseInt(br.readLine());
            }
        }

        System.out.println("ingrese valores de la segunda matriz");
        for(int i=0;i<tam;i++){
            for(int j=0;j<tam;j++){
                System.out.println("ingrese valor posicion "+i+"-"+j);
                matriz2[i][j] = Integer.parseInt(br.readLine());
            }
        }

        int opcion = 0;

        do{
            System.out.println("------------- opciones -------------");
            System.out.println("1-suma");
            System.out.println("2-multiplicacion");
            System.out.println("3-resta");
            //System.out.println("4-division");
            System.out.println("0-salir");

            System.out.print("Ingrese opcion: ");
            opcion = Integer.parseInt(br.readLine());

            if(opcion == 1){
                matriz = op.suma(matriz1, matriz2);
                System.out.println("Suma:");
            }

            if(opcion == 2){
                matriz = op.multipliacion(matriz1, matriz2);
                System.out.println("Multiplicacion:");
            }

            if(opcion == 3){
                matriz = op.resta(matriz1, matriz2);
                System.out.println("Resta:");
            }

            /*if(opcion == 4){
                //matriz = op.suma(matriz1, matriz2);
                System.out.println("Division:");
            }*/

            if(opcion != 1 && opcion != 2 && opcion != 3){
                System.out.println("Opcion Invalida");
            }else{
                for(int i=0;i<tam;i++){
                    for(int j=0;j<tam;j++){
                        System.out.print(matriz[i][j]);
                    }
                    System.out.println();
                }
            }


        }while(opcion != 0);

    }

}
