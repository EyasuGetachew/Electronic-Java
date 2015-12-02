# Electronic-Java
This does different electronic purchase transaction
public abstract class Electronic{
    private String brand;   
    private double price;       //in birr
    private int warranty;       //in months    
      
    public Electronic(String b, double p, int w){
        brand = b;        
        price = p;
        warranty =w;        
    }
    
    public double getPrice(){ return price; }
    public void setPrice(double p){  price =p;  }
    public int getWarranty(){ return warranty; }    
    public void setWarranty(int w){ warranty = w; } 
    
    public void print(){
        System.out.println("\nBrand: " + brand + ";  Price: birr" + price+ ";  Warranty: " + warranty + " months");        
    }    
}




public class CellPhone extends Electronic{
    private double batteryLife;     //in hours
    private boolean webEnabled;
  
    public CellPhone(String brand, double price, int warranty, double bL, boolean wE){
        super(brand, price, warranty);
        batteryLife = bL;
        webEnabled = wE;        
    }
   
    public void print(){
        super.print();
        System.out.println("Battery Life: " + batteryLife + "Hr;  Web Enabled: " + webEnabled);
    }  
}







public class Computer extends Electronic{
    private int cpu;       //speed in MHz
    private int memory;         //size in MB
       
    public Computer(String brand, double price, int warranty, int c, int m){
        super(brand, price, warranty);
        cpu = c;
        memory =m;        
    }
    
    public void print(){
        super.print();
        System.out.println("CPU Speed: " + cpu + "MHz;  Memory Size: " + memory+ "MB");
    }     
}





public class Laptop extends Computer { 
    private double displaySize;   //size in inches    
    
    public Laptop(String brand, double price, int warranty, int cpu, int memory, double d){
        super( brand, price, warranty, cpu,  memory);
        displaySize = d;        
    }
    
    public void print(){
        super.print();
        System.out.println("Display Size: " + displaySize + "''");
    }
}





public class ElectronicMain {
    public static void main (String args[]) {
        
        Electronic [] e=new Electronic[3];
        e[0] = new CellPhone("Nokia TS200",3000, 18, 3.5, true);
        e[1] = new Computer("Dell D2100", 10000, 24, 1500, 512);
        e[2] = new Laptop("HP N5170", 15000, 24, 900, 256, 15);
        
        for (int i=0; i<3; i++)
            e[i].print();
    }
}

















