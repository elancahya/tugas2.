# tugas2.
package benda;


    import java.util.Scanner;
import java.util.InputMismatchException;
public class Benda {

    /**
     * @param args the command line arguments
     */
   


   

    Scanner run = new Scanner(System.in);
    int semua;

    int[] kodebarang = new int[20];
    int[] harga = new int[20];
    int[] stock = new int[20];
    int[] nilai = new int[20];
    String[] name = new String[20];

    public Benda(){

    }
    public void masukkanData(){
        try{
            for(int i=0;i < semua;i++){
                System.out.println("Produk nomer"+(i+1));
                System.out.println("name produk \t \ttekan 0 jika tidak jadi : ");

                run.nextLine();
                kodebarang[i]=i+1;
                name[i] = run.nextLine();

                if (name[i].equals("0")){
                    break;
                }

                System.out.println("harga produk : ");
                harga[i]= run.nextInt();
                System.out.println("stock produk : ");
                stock[i]= run.nextInt();
                nilai[i]=stock[i]*harga[i];
            }
        }catch (InputMismatchException e){
            System.out.println("nomer yang anda masukkan wajib angka ");
            run.nextLine();
            menu();
        }
    }
    public void menu(){
        do{
            System.out.println("memasukkan nomer produk : ");
            semua = run.nextInt();

            if (semua <= 0){
                System.out.println("yang anda masukkan wajib lebih dari 0");
            }else {
                masukkanData();
            }
        }while (semua <= 0);
    }
    public void getnilaidata(){
        for (int i =0; i < semua; i++){
            System.out.println("nomer produk : "+kodebarang[i]);
            System.out.println("nama produk : "+ name[i]);
            System.out.println("harga produk : "+harga[i]);
            System.out.println("stock produk : "+stock[i]);
            System.out.println("nilai produk : "+nilai[i]);
        }
    }

}
    
    
    
    
    
    
    
   
public class Main {
    public static void main(String[] args) {
        Benda produk = new Benda();
        produk.menu();
        produk.getnilaidata();
    }
     
}
    
    
    
