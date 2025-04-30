# ejercicios
ejercicios 

package EjerciciosM;
import java.util.Scanner; 
import java.util.ArrayList;

public class Registro {

   
    public static class Usuario {
        String nombre;
        int edad;
        String estado;

      
        public Usuario(String nombre, int edad, String estado) {
            this.nombre = nombre;
            this.edad = edad;
            this.estado = estado;
        }
    }

    public static void main(String[] args) {
       
        Scanner scanner = new Scanner(System.in);

        // Crear una lista para almacenar los usuarios que van a ingresar
        ArrayList<Usuario> lista = new ArrayList<>();

        // Preguntar cuántos usuarios se desean ingresar
        System.out.print("¿Cuántos usuarios deseas registrar? ");
        int total = scanner.nextInt();
        scanner.nextLine(); // Limpiar el buffer

        // Recolectar los datos de los usuarios
        for (int i = 0; i < total; i++) {
            System.out.print("Ingresa nombre del usuario " + (i + 1) + ": ");
            String nombre = scanner.nextLine();

            System.out.print("Ingresa edad del usuario " + (i + 1) + ": ");
            int edad = scanner.nextInt();
            

            System.out.print("Ingresa estado (Activo/Inactivo) del usuario " + (i + 1) + ": ");
            String estado = scanner.nextLine();


            Usuario usuario = new Usuario(nombre, edad, estado);
            lista.add(usuario);
        }

        // Contadores para mayores y menores de edad
        int mayores = 0;
        int menores = 0;

     
        for (Usuario usuario : lista) {
            if (usuario.edad >= 18) {
                System.out.println(usuario.nombre + " – Edad: " + usuario.edad + " – Estado: " + usuario.estado + " – MAYOR de edad");
                mayores++;
            } else {
                System.out.println(usuario.nombre + " – Edad: " + usuario.edad + " – Estado: " + usuario.estado + " – MENOR de edad");
                menores++;
            }
        }

        // Imprimir el resumen
        System.out.println("\nResumen:");
        System.out.println("Total de usuarios registrados: " + lista.size());
        System.out.println("Usuarios mayores de edad: " + mayores);
        System.out.println("Usuarios menores de edad: " + menores);

    }
}
