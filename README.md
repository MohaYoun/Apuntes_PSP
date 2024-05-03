# Apuntes_PSP
Cosas interesantes y fallos cometidos.

### Ejercicio 1 de pract Junio
1. Fallos Cometidos.
   1.1 Leer el pipe de escritura en proceso hijo y poner que en el sizeof(numeros) en vez de sizeof(int).
   Codigo Bueno:
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

### Ejercio 2 de pract Junio.
1. Fallos Cometidos.
   1.1 Repartir el trabajo para cada proceso hijo.
   Codigo Bueno:
   ```
   for (int c1 = n1; c1 < n2; c1++)
   {
      if (c1 % n_proc == i)
      {
         if(comprobarCapicua(c1))
         {
         printf("El numero %d es capicua pid= %d.\n", c1, getpid());
         }
      }
   }
   ```
   El fallo cometido en la comprobacion del numero modulo n_procesos == pid, en vez de i que seria cada proceso y otro fallo es este
   if (c1 % i == pid).
