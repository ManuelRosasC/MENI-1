# MENI-1
PROYECTO UNO
#include <stdio.h>

// --- FUNCIONES ---

float retirar (float saldoActual, float monto){
    float nuevoSaldo;
    nuevoSaldo = saldoActual - monto;
    return nuevoSaldo;
}

float depositar(float saldoActual, float monto) {
    float nuevoSaldo;
    nuevoSaldo = saldoActual + monto;
    return nuevoSaldo;
}

void consultarSaldo(float saldo) {
    printf("Su saldo actual es: $%.2f\n", saldo);
}


// --- PROGRAMA PRINCIPAL ---

int main() 
{
    float saldoActual = 1000.0;
    float montoARetirar;
    float montoADepositar;
    int opcion; 
// Hola
    // Inicio del ciclo do-while
    do {
        // Menú de opciones visual
        printf("\n--- MENU BANCO ---\n");
        printf("1. Consultar Saldo\n");
        printf("2. Depositar Dinero\n");
        printf("3. Retirar Dinero\n");
        printf("4. Salir del programa\n"); 
        printf("Seleccione una opcion (1-4): ");
        scanf("%d", &opcion);
        printf("\n");

        // Estructura de decisiones
        switch(opcion) {
            case 1:
                consultarSaldo(saldoActual);
                break;
                
            case 2:
                printf("Ingrese el monto que desea depositar: ");
                scanf("%f", &montoADepositar);
                saldoActual = depositar(saldoActual, montoADepositar);
                printf("Deposito exitoso. ");
                consultarSaldo(saldoActual);
                break;
                
            case 3:
                printf("Cual es el monto que va a retirar: ");
                scanf("%f", &montoARetirar);
                saldoActual = retirar(saldoActual, montoARetirar);
                printf("Retiro exitoso. ");
                consultarSaldo(saldoActual);
                break;
                
            case 4:
                printf("Gracias por usar el sistema bancario. ¡Hasta luego!\n");
                break;
                
            default:
                printf("Opcion invalida. Intente de nuevo.\n");
                break;
        }

    } while(opcion != 4); // El ciclo se repite MIENTRAS la opción NO sea 4
    
  

    return 0;
}
