# Apuntes_PSP
Cosas interesantes y fallos cometidos.

### Ejercicio 1 de pract Junio
1. Fallos Cometidos.
   1.1 Leer el pipe de escritura en proceso hijo y poner que en el sizeof(numeros) en vez de:
   ```
   if (pid == 0)
    {
    // proceso hijo
    close(fd[WRITE]);
    int numeros[n_aleatorios];
    read(fd[READ], numeros, n_aleatorios * sizeof(int));
    for (int i = 0; i < n_aleatorios; i++)
    {
    printf("numero recibido %d \n", numeros[i]);
    }
    close(fd[READ]);
   ```
   Al poner sizeof(numeros) me cogia el tamaño de bytes de n_aleatorios por estar definido como tamaño de array de la variable.

   
