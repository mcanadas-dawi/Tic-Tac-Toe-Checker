# TIC-TAC-TOE CHECKER
## CODEWARS 5KYU KATA
### TAREA
Queremos comprobar el ganador del clásico juego Tic-Tac-Toe.
Supongamos que el tablero tiene la forma de una matriz de 3x3, donde el valor es 0 si un lugar está vacío, 1 si es una "X" o 2 si es una "O", así:

[[0, 0, 1],
  
 [0, 1, 2],
 
 [2, 1, 0]]
### REGLAS
- **Return -1** si el tablero aún no está terminado Y nadie ha ganado todavía (hay espacios vacíos).
- **Return 1** si ganó "X".
- **Return 2** si "O" ganó.
- **Return 0** si es empate.
Puedes suponer que el tablero recibido es válido en el contexto de un juego de Tic-Tac-Toe.

### CÓDIGO
```java
public static int isSolved(int[][] board) {
	//Comprobar ganador 
	 for (int i=1; i<=2; i++) {
            for (int j=0; j<=board.length-1; j++) {
		//Comprobar fila
                if (board[j][0] == i && board[j][i] == i && board[j][2] == i) {
                    return i;
                }
		//Comprobar columna
                if (board[0][j] == i && board[1][j] == i && board[2][j] == i) {
                    return i;
                }
            }
            //Comprobar diagonales
            if ((board[0][0]==i && board[1][1]==i && board[2][2]==i) || 
			(board[0][2]==i && board[1][1]==i && board[2][0]==i)) {
                return i;
            }
        }
	//Comprobar si el tablero esta terminado
        for (int i=0; i<=board.length-1; i++) {
            for (int j=0; j<=board.length-1; j++) {
                if (board[i][j] == 0) {
                    return -1;
                }
            }
        }
	//Si ninguna de las anteriores se cumple, empate
        return 0;
    }
}
```
### ENLACE AL KATA
[Tik-tak-toe Link](https://www.codewars.com/kata/525caa5c1bf619d28c000335/java)
