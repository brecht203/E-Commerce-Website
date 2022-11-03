
package ecommerce.ea;
import java.util.*;

/* Members:
 *   Marquita, Brecht
 *   Pagaran, Feliciano Sherdy E.
 *   Canoy, Beverly
 *
 *  Date:
 *   October 21,2022
 *
 *  Title of the Project:
 *n
Ecommerce Website
*/

public class EA {
    
    private static List<Userlist>userList = new ArrayList<>();
    private static List<Items>itemList = new ArrayList<>();
    private static List<Cart>addtoCart = new ArrayList<>();
    public static int ID, AGE,sum;
    public static String NAME,EMAIL,USERNAME,PASSWORD,confirmPass,loginUser,loginPass,CARTNAME;
    public static String currentsessionuser,currentsessionpass;
    public static String PRODNAME,ADDRESS;
    public static int PRICE,CARTPRICE;
    public static char charlang;
    public static Scanner scan = new Scanner(System.in);
    
    // DIRI MAG INPUT ANG USER PARA SA IYANG PERSONAL INFORMATION
    // LIKE NAME EMAIL UG PASS
    private static void addUser()
    {
        scan.nextLine();
        System.out.println("\n\n             SIGN UP             \n");
        System.out.print("Enter Name: ");
        NAME = scan.nextLine();
        System.out.print("Enter Age: ");
        AGE = scan.nextInt();
        scan.nextLine();
        System.out.print("Enter Email: ");
        EMAIL = scan.nextLine();
        System.out.print("Enter Address: ");
        ADDRESS = scan.nextLine();
        System.out.print("Enter Username: ");
        USERNAME = scan.nextLine();
        System.out.print("Enter Password: ");
        PASSWORD = scan.nextLine();
        System.out.print("Please Confirm your Password: ");
        confirmPass = scan.nextLine();

    } 
    
    // MAO NEY VALIDATION PARA I CONFIRM IF ANG PASSWORD NGA GI INPUT
    // IS SAME BA SA CONFIRM PASSWORD
    private static Userlist Confirm()
    {
        addUser();
        Userlist users = new Userlist(ID, NAME, AGE,ADDRESS, USERNAME, EMAIL, PASSWORD);
        if(PASSWORD.equals(confirmPass))
        {
        userList.add(users);
        System.out.print("\n     SUCCESSFULLY SIGNED-UP     \n\n");
        }
        else
        {
            System.out.println("Password Not The Same... Try Again...");
            addUser();
        }
        return users;
    }
    /* DIRI  DAAYUN  ANG KATONG LOGIN LOGIN
     * MANGAYO SIYA UG USERNAME UG PASSWORD
     * MAG ITERATE SIYA OR IYANG I SEARCH ANG
     * LIST SA DATA NGA GI INPUT IF ANG
     * USERNAME NGA IMONG GI INPUT IS NAG MATCH BA
     * DADTO SA MGA NAKA SET NGA DATA OR DATA NGA GIPANG
     * INPUT. IF ANG DATA NGA GI INPUT IS DILI MATCH
     * SA DATA NGA NAKA SET SA ARRAYLIST MAG SEND SIYA
     * UG MESSAGE NGA INVALID CREDENTIALS
     * PERO IF MATCH GANI IYA KANG I PADALA SA HOMEPAGE()
     * NGA FUNCTION.
    */
    private static void Login()
    {
        scan.nextLine();
        System.out.println("\n\n              LOGIN              \n");
        System.out.print("Enter Username: ");
        loginUser = scan.nextLine();
        System.out.print("Enter Password: ");
        loginPass = scan.nextLine();
        
        for(Userlist users : userList)
        {
            if((users.getUSERNAME().equals(loginUser) && users.getPASSWORD().equals(loginPass)))
            {
                System.out.println("\n\n       SUCCESSFULLY LOGIN         ");
                CurrentSession();
                Homepage();
            }
            else //if(!users.getUSERNAME().equals(loginUser) && !users.getPASSWORD().equals(loginPass))
            {
                System.out.println("\n\n          INVALID CREDENTIALS        ");
                RunMe();
            }
        }
    }
    
    /*DIRI I SET SA IMONG PROGRAM TONG IMONG
     * GI INPUT NGA CREDENTIALS SA LOGIN
     * PARA INIG PRINT KATO RA NGA DATA
     * ANG IYANG PANGITAON SA LIST IF EVER
     * GUSTO NIMO MA KITA ANG IMONG PERSONAL DATA
     */
    private static void CurrentSession(){
        currentsessionuser = loginUser;
        currentsessionpass = loginPass;
       
        
    }
    
     /*MAO NI SIYA ANG IMONG HOMEPAGE BAY
     * DIRI KA MAG PILI SA KATONG MGA CHOICES NGA NAA DIRI
     */
    private static void Homepage(){
        int choose = 0;
       while(choose != 5){
        System.out.println("\n\n");
        System.out.println("|----------------------------------|");
        System.out.println("+       WELCOME DEAR CUSTOMER      +");
        System.out.println("|----------------------------------|");
        System.out.println("+------What do you want to do?-----+");
        System.out.println("|                                  |");
        System.out.println("+ 1. Show User Information         +");
        System.out.println("|                                  |");
        System.out.println("+ 2. Show Item List                +");
        System.out.println("|                                  |");
        System.out.println("+ 3. Go Shopping                   +");
        System.out.println("|                                  |");
        System.out.println("+ 4. Cart Items                    +");
        System.out.println("|                                  |");
        System.out.println("+ 5. Logout                        +");
        System.out.println("+----------------------------------+");
        System.out.print("Option: ");
        try{
        choose = scan.nextInt();
        }
        catch(Exception ex){
        System.out.print("\n\nInvalid Input Please Try Again......");
        scan.next();
        continue;
        }
        switch(choose)
        {
            case 1: Print(); break;
            case 2: ItemList(); break;
            case 3: AddtoCart(); break;
            case 4: cartItems(); break;
            case 5: RunMe(); break;
        }
       }
    }
    private static void cartItems()
    {
        System.out.println("\n\nPRODUCTS IN YOUR CART: ");
        for(Cart carts : addtoCart)
        {
            System.out.println("Product Name: " + carts.getprodname()
            + "\nProduct Price: " + carts.getprice() + "\n");
        }
      
    }

    /*DIRI DAYUN ANG ADD TO CART
     * MAG PILI KA UG KATONG MGA ITEM
     * ONCE MAKA PILI KA, KATONG MGA ITEM NGA IMONG
     * GIPANG PILI MA SEND TO SYA SA GETTERS SETTERS SA CART
     * DADTO NIYA I SET ANG MGA DATA SA ITEMS NGA IMONG GI PANG PIILI
     * LIKE PRODUCT NAME UG PRICE.
     * IF OK NAKA SA MGA ITEMS NGA IMONG GI PANG PILI
     * PWEDE NAKA MO PROCEED SA CHECKOUT
     */
    
     private static void AddtoCart(){
      int choice = 0;
     
        System.out.println("\n\n");
        System.out.println("+-----------------------------------+");
        System.out.println("|            SECRET SHOP            |");
        System.out.println("+-----------------------------------+");
        System.out.println("|-------CHOOSE PRODUCT ABOVE?-------|");
        System.out.println("+                                   +");
        System.out.println("|                                   |");
        System.out.println("+ ENTER NUMBER [1-5] FOR ITEMS      +");
        System.out.println("|                                   |");
        System.out.println("+ ENTER NUMBER [6] TO ADD CART      +");
        System.out.println("|                                   |");
        System.out.println("+ ENTER NUMBER [7] TO CHECKOUT      +");
        System.out.println("|                                   |");
        System.out.println("+ ENTER NUMBER [8] TO BACK HOMEPAGE +");
        System.out.println("|                                   |");
        System.out.println("+                                   +");
        System.out.println("+-----------------------------------+");
        System.out.print("Option: ");
    
      for(Items items: itemList)
      {
          System.out.println("\n" + items.getpid() 
            + "\n| Product Name: " + items.getprodname()
            + "\n| Price: " + items.getprice()
            + "\n| Stocks: " + items.getstocks()
            + "\n| Status: " + items.getstatus());
      }
      
      
      while(choice != 99){
        System.out.print("Option: ");
         try{
      choice = scan.nextInt();
         }
         catch(Exception ex){
        System.out.print("\n\nInvalid Input Please Try Again......\n\n");
        scan.next();
        continue;
        }
      switch(choice){
        case 1: 
      
        for(Items items: itemList)
        {
            if(items.getpid() == 1)
            {
                int cs = items.getstocks();
                int ns = cs - 1;
                if(items.getstatus().equals("Out of Stock"))
                {
                    System.out.println("Product out of stock");
                    AddtoCart();
                }
                items.setstocks(ns );
            }
        }          
        int id = itemList.get(0).getpid();
        String prodname = itemList.get(0).getprodname();
        int price = itemList.get(0).getprice();
        Cart addcart1 = new Cart(id, prodname, price );
        addtoCart.add(addcart1);
        break;
        
         case 2: 
        for(Items items: itemList)
        {
            if(items.getpid() == 2)
            {
                int cs = items.getstocks();
                int ns = cs - 1;
                if(items.getstatus().equals("Out of Stock"))
                {
                    System.out.println("Product out of stock");
                    AddtoCart();
                }
                items.setstocks(ns );
            }
        }          
             
        id = itemList.get(1).getpid();
        prodname = itemList.get(1).getprodname();
        price = itemList.get(1).getprice();
        Cart addcart2 = new Cart(id, prodname, price );
        addtoCart.add(addcart2);
       
            break;
        

        case 3:
        for(Items items: itemList)
        {
            if(items.getpid() == 3)
            {
                int cs = items.getstocks();
                int ns = cs - 1;
                if(items.getstatus().equals("Out of Stock"))
                {
                    System.out.println("Product out of stock");
                    AddtoCart();
                }
                items.setstocks(ns );
            }
        }          
            
        id = itemList.get(2).getpid();
        prodname = itemList.get(2).getprodname();
        price = itemList.get(2).getprice();
        Cart addcart3 = new Cart(id, prodname, price );
        addtoCart.add(addcart3);
       
            break;

        case 4:  
        for(Items items: itemList)
        {
            if(items.getpid() == 4)
            {
                int cs = items.getstocks();
                int ns = cs - 1;
                if(items.getstatus().equals("Out of Stock"))
                {
                    System.out.println("Product out of stock");
                    AddtoCart();
                }
                items.setstocks(ns );
            }
        }          
            
        id = itemList.get(3).getpid();
        prodname = itemList.get(3).getprodname();
        price = itemList.get(3).getprice();
        Cart addcart4 = new Cart(id, prodname, price );
        addtoCart.add(addcart4);
       
                break;

        case 5: 
        for(Items items: itemList)
        {
            if(items.getpid() == 5)
            {
                int cs = items.getstocks();
                int ns = cs - 1;
                if(items.getstatus().equals("Out of Stock"))
                {
                    System.out.println("Product out of stock");
                    AddtoCart();
                }
                items.setstocks(ns );
            }
        }          
        id = itemList.get(4).getpid();
        prodname = itemList.get(4).getprodname();
        price = itemList.get(4).getprice();
        Cart addcart5 = new Cart(id, prodname, price );
        addtoCart.add(addcart5);
        
            break;

        case 6:       
        System.out.println("\n\nPRODUCTS IN YOUR CART:  ");
        for(Cart carts : addtoCart){
            System.out.println("Product Name: " + carts.getprodname()
            + "\nProduct Price: " + carts.getprice()+ "\n");
        }
        break;

        case 7: 
                //System.out.println("You want to proceed to checkout?");
              //  System.out.println("Press 'y' for Yes 'n' for No");
        System.out.println("\n\n");
        System.out.println("+-----------------------------------------------------------------+");
        System.out.println("|----------------------PROCEED TO CHECKOUT?-----------------------|");
        System.out.println("+                                                                 +");
        System.out.println("|                                                                 |");
        System.out.println("+ PRESS [Y] IF YES (PRINT RECEIPT ,CLEAR CART ITEMS & GO HOMEPAGE +");
        System.out.println("|                                                                 |");
        System.out.println("+ PRESS [N] IF NO  (SAVE ITEM CHOICE TO CART & BACK HOMEPAGE)     +");
        System.out.println("|                                                                 |");
        System.out.println("+                                                                 +");
        System.out.println("+-----------------------------------------------------------------+");
        System.out.print("Option: ");
                scan.nextLine(); 
                choice = scan.next().charAt(0);
                switch(choice){
                    case 'Y' :
                    case 'y' : 
                System.out.println("+--------------------------------------------------+");
                System.out.println("|               SECRET SHOP RECEIPT                |");
                System.out.println("|   Villarin Street, Carmen, Cagayan de Oro City   |");
                System.out.println("|               CUSTOMER INVOICE                   |");
                System.out.println("+--------------------------------------------------+");
                System.out.println("|  Cashier Name: Brecht                            |");
                System.out.println("|  INVOICE NO: 458-80-108                          |");
                System.out.println("+--------------------------------------------------+");
                System.out.println("|   Customer Name: " + currentsessionuser + "        |");
                System.out.println("|   Customer Address: " + ADDRESS + "                |");
                System.out.println("+--------------------------------------------------+");
                for(Cart items : addtoCart){
                System.out.println(items.getprodname() + " = " + items.getprice());
                System.out.println("+--------------------------------------------------+");
                }
                for(Items items: itemList)
                {
                    if(items.getpid() == 1)
                    {
                    if(items.getstocks() == 0)
                        {
                    String status = "Out of Stock";
                    items.setstatus(status);
                  
                        }
                    }
                }
                for(Items items: itemList)
                {
                    if(items.getpid() == 2)
                    {
                    if(items.getstocks() == 0)
                        {
                    String status = "Out of Stock";
                    items.setstatus(status);
                  
                        }
                    }
                }
                for(Items items: itemList)
                {
                    if(items.getpid() == 3)
                    {
                    if(items.getstocks() == 0)
                        {
                    String status = "Out of Stock";
                    items.setstatus(status);
                  
                        }
                    }
                }
                for(Items items: itemList)
                {
                    if(items.getpid() == 4)
                    {
                    if(items.getstocks() == 0)
                        {
                    String status = "Out of Stock";
                    items.setstatus(status);
                  
                        }
                    }
                }
                for(Items items: itemList)
                {
                    if(items.getpid() == 5)
                    {
                    if(items.getstocks() == 0)
                        {
                    String status = "Out of Stock";
                    items.setstatus(status);
                  
                        }
                    }
                }
                CheckOut();
                addtoCart.clear();
                Homepage();
                break;
                case 'N': break;
                case 'n': break;
                }
        case 8:
            Homepage();break;
                
        }
       
      }

    }
    
     /*KINI SIYA NGA PART SA CODE IS MAO NI ANG MAG ADD SA TOTAL VALUE SA IMONG MGA ITEM
     * KIBALI STARTING NIYA IS SUM = 0;
     * MAG SCAN NA SIYA SA LIST OF PRICES ATONG MGA ITEMS NGA GIPANG PILI NIMO
     * IYA NANG ISA ISA HON UG BUTANG 
     * FOR EXAMPLE ANG MGA PRICES KAY 10,20,30
     * ANG MAHITABO ANA KAY SUM = 0 + 10 = 10;
     * SUM 10 + 20 = 30;
     * SUM 30 + 30 = 60;
     * SO KIBALI ANG TOTAL TANAN SA ITEM IS 60;
     */
    private static int CheckOut()
    {
            sum = 0;
           for(Cart total : addtoCart)
           {
            sum += total.getprice();        
           }
           System.out.println("+--------------------------------------------------+");
           System.out.println("|  TOTAL AMOUNT: " + sum + " PESO/S                +");
           System.out.println("|  HAVE A GOOD DAY!                                |");
           System.out.println("+--------------------------------------------------+");
           return sum;
    }
    
     /*MAG SCAN OR ITERATE NI SIYA SA TANAN USERS
     * AND IF ANG USERNAME IS MATCH SA CURRENTSESSIONUSER
     * IYANG I PRINT ANG DETAILS ANA NGA USER
     */
    private static void Print(){
        for(Userlist users : userList){
            if(users.getUSERNAME().equals(currentsessionuser)){
                System.out.println("\n\nName: " + users.getNAME()
                + "\nAge: " + users.getAGE()
                +"\nUsername: " + users.getUSERNAME()
                +"\nEmail: " + users.getEMAIL()
                +"\nAddress: " + users.getADDRESS());
            }
        }
    }


    /*MAO NI ANG PRODUCT LIST.
     * DIRI RAMO MAG ADD UG MGA PRODUCTS UG PRICES
     * TAPOS MAG ITERATE MO ANANG ARRAY PARA MAOY I SET NINYO AS ARRAYLIST VALUE
     * PARA SA INYONG ITEMLIST
     */
    
    private static void ProductList()
    {
       Items item1 = new Items(1,2400,"ADATA 1TB HD330 DURABLE EXTERNAL HDD BLK",10, "Available");
       Items item2 = new Items(2,26000,"PC RX6600XT RED DEVIL 8GB GDRR6 128BIT Graphics Card",10, "Available");
       Items item3 = new Items(3,13650,"PC RX6500XT ITX 4GB GDDR6 64BIT Graphics Card",10, "Available");
       Items item4 = new Items(4,10350,"PC RX6400 (4GBD6-DH) 4GB GDDR6 64BIT Graphics Card",10, "Available");
       Items item5 = new Items(5,45000,"PALIT RTX3070TI GAME ROCK 8GB GDDR6 256BIT Graphics Card",10, "Available");
       
       itemList.add(item1);
       itemList.add(item2);
       itemList.add(item3);
       itemList.add(item4);
       itemList.add(item5);
    }
    
    /*PRINT RANI SIYA SA MGA ITEMS NGA NAKA LISTA SA PRODUCTLIST */
    private static void ItemList()
    {
        System.out.println("+------------------------------------------------------------------------+");
        System.out.println("|                              ITEMS LIST                                |");
        System.out.println("+------------------------------------------------------------------------+");
        for(Items item : itemList)
        {
        System.out.println("| Product Name: " + item.getprodname()
        + "\n| Price: " + item.getprice()
        + "\n| Stocks: " + item.getstocks()
        + "\n| Status: " + item.getstatus());
        System.out.println("|------------------------------------------------------------------------|");
        }
    }
    /*MURA NI SIYA KIBALI UG MAINFUNCTION PERO LAHI LANG ANG VARIABLE NAME
     * MAG ASK SIYA IF NAA BA KAY ACCOUNT OR WALA
     * IF NAA PROCEED SA LOGIN
     * IF WALA PROCEED SA ADDUSER
     */
    public static void RunMe()
    {
       while(charlang != 'e')
       {
       
        System.out.println("\n\n");
        System.out.println("+----------------------------------+");
        System.out.println("|      WELCOME TO SECRET SHOP      |");
        System.out.println("+----------------------------------+");
        System.out.println("|-----ALREADY HAVE AN ACCOUNT?-----|");
        System.out.println("+                                  +");
        System.out.println("|                                  |");
        System.out.println("+ PRESS [Y] IF YES (LOGIN)         +");
        System.out.println("|                                  |"); 
        System.out.println("+ PRESS [N] IF NO  (SIGN UP)       +");
        System.out.println("|                                  |");
        System.out.println("+ PRESS [E] FOR EXIT  (END)        +");
        System.out.println("|                                  |");
        System.out.println("+                                  +");
        System.out.println("+----------------------------------+");
        System.out.print("Option: ");charlang = scan.next().charAt(0);
            switch(charlang)
            {
            case 'Y': Login(); break;
            case 'y': Login(); break;
            case 'N': Confirm(); break;
            case 'n': Confirm(); break;
            case 'E': System.exit(0);
            case 'e': System.exit(0);
            }
       }
    }
    public static void main(String[] args) 
    {
        ProductList();
        RunMe();
    }
    
}
