# calculadora

/**@param:Int o Double asignado por el usario
 * @author: Maria Camila CHacon
 * @Date:12/09/2017
 * @return:resultado
 */

import java.io.*;/* traer la clase java. io*/
public class calcu {
	static BufferedReader br = new BufferedReader (new InputStreamReader(System.in));
	static BufferedWriter bw = new BufferedWriter (new OutputStreamWriter(System.out));
	public static void main(String[] args) throws IOException {/*seleccionar del menú una función matemática*/
		int option;
		int[] parameters;
		do{
			option=getOption();
			parameters= getParameters(option);
			makeOperation(option,parameters);
		}
		while (option !=12);
			
		bw.write(getOption());
		bw.flush();
	}
	public static int getOption() throws IOException{
		bw.write("\n\nSeleccione por favor una de las siguientes opciones:\n"+"1.suma\n2. Resta\n3. multiplicación\n4. Disvisión\n5. Modulo\n"
	              +"6. Potencia\n7. Facotrial\n8. Seno\n9. Coseno\n10. Integral\n11. Cuadratica\n12. salir\n");
	    bw.flush();        
		int option=Integer.parseInt(br.readLine() );
		
		return option;
	}
	@SuppressWarnings("null")
	public static int[] getParameters(int option) throws IOException{/*Se ingresan los valores según se requiera para la operación*/
		int [] parameters=null;
		
		switch(option){
		case 1: //suma 
			{
				parameters=new int [2];
			bw.write("\nA continuacion se va a realizar una operacion de suma. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());
		}
		break;
        case 2: //resta
        {
        	parameters=new int [2];
        	bw.write("\nA continuacion se va a realizar una operacion de resta. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());	
		}
		break;
        case 3://multiplicación
        {
        	parameters=new int [2];
        	bw.write("\nA continuacion se va a realizar una operacion de multiplicacion. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());
        }
        break;
        case 4://division
        {
        	parameters=new int [2];
        	bw.write("\nA continuacion se va a realizar una operacion de division. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());
        }
        break;
        case 5://modulo
        {
        	parameters=new int [2];
        	bw.write("\nA continuacion se va a realizar una operacion de modulo. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());
        }
       break;
		case 6://potencia
		{
			parameters=new int [2];
			bw.write("\nA continuacion se va a realizar una operacion de potencia. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());	
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());
		}
		break;
        case 7:{//factorial
        	parameters=new int [1];
			bw.write("\nA continuacion se va a realizar una operacion de factorial. \n");
			bw.write("ingrese el numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
		}
		break;
        case 8://seno
        {
        	parameters=new int [1];
        	bw.write("\nA continuacion se va a realizar una operacion de seno. \n");
			bw.write("ingrese el numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
        }
        break;
        case 9://coseno
        {
        	parameters=new int [1];
        	bw.write("\nA continuacion se va a realizar una operacion de coseno. \n");
			bw.write("ingrese el numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
        }
        break;
        case 10://integral
        {
        	parameters=new int [3];
        	bw.write("\nA continuacion se va a realizar una operacion de integral. \n");
        	bw.write("ingrese el primer limite: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());	
			bw.write("ingrese el segundo limite: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());	
			bw.write("ingrese el paso: ");
			bw.flush();
			parameters[2]= Integer.parseInt( br.readLine());	
        }
       break;
        case 11://funcion cuadratica
        {
        	parameters=new int [3];
        	bw.write("\nA continuacion se va a realizar una operacion de función cuadratica. \n");
			bw.write("ingrese el primer numero: ");
			bw.flush();
			parameters[0]= Integer.parseInt( br.readLine());
  
			bw.write("ingrese el segundo numero: ");
			bw.flush();
			parameters[1]= Integer.parseInt( br.readLine());

			bw.write("ingrese el tercer numero: ");
			bw.flush();
			parameters[2]= Integer.parseInt( br.readLine());
        }
        break;
       
        
       default:{
    	    System.exit(0);
       }
    	break;   
		}
		return parameters;
	}
	public static void makeOperation(int option, int[] parameters) throws IOException{/*se da el resultado de la operación*/
		Calculadoras oper = new Calculadoras();
		switch(option){
		case 1://suma
		{
			double result=oper.suma(parameters[0], parameters [1]);
			bw.write("el resultado de la suma es :"+result + "\n");
			bw.flush();
		}
			break;
		case 2://resta
		{
			double result=oper.resta(parameters[0], parameters [1]);
			bw.write("el resultado de la resta es :"+result + "\n");
			bw.flush();
		}
			break;
		
		case 3://multiplicación
		{
			double result=oper.multiplicación(parameters[0], parameters [1]);
			bw.write("el resultado de la multiplicacion es :"+result + "\n");
			bw.flush();
		}
			break;
		case 4://división
		{
			double result=oper.division(parameters[0], parameters [1]);
			bw.write("el resultado de la division es :"+result + "\n");
			bw.flush();
		}
			break;
		case 5://modulo
		{
			double result=oper.modulo(parameters[0], parameters [1]);
			bw.write("el resultado del modulo entre "+parameters[0] + " y "+ parameters[1] + " es: "+ result + "\n");
			bw.flush();
		}
			break;
		case 6://potencia
		{
			double result=oper.potencia(parameters[0], parameters [1]);
			bw.write("el resultado de la potencia es :"+result + "\n");
			bw.flush();
		}
			break;
		case 7://factorial
		{
			int result=oper.f_factorial(parameters[0]);
			bw.write("el resultado del factorial es :"+result + "\n");
			bw.flush();
		}
			break;
		case 8://seno
		{
			double result=oper.sin(parameters[0]);
			bw.write("el resultado del seno es :"+result + "\n");
			bw.flush();
		}
			break;
		case 9://coseno
		{
			double result=oper.cos(parameters[0]);
			bw.write("el resultado del coseno es :"+result + "\n");
			bw.flush();
		}
			break;
		case 10://integral
		{
			double result=oper.integral(parameters[0], parameters[1], parameters[2]);
			bw.write("el resultado de la integral es :"+result + "\n");
			bw.flush();
		}
			break;
		case 11://funcion cuadratica
		{
			int[] fun=oper.f_cuadratica(parameters[0], parameters [1], parameters [2]);
			bw.write("el resusltado de x1 es: "+fun[0]+" el resultado de x2 es: "+ fun[1]);
			bw.flush();
		}
			break;
		

		}	
	}
}
/**@param:Int o Double asignado por el usario
 * @author: Maria Camila CHacon
 * @Date:12/09/2017
 * @return:resultado
 */

public class Calculadoras {/*El paso a paso de las operaciones, y sus condicionales*/
	

	public static double suma(double x, double y){
		double t=x+y;
		return t;
	}

		public static double resta (double x, double y){
			double t=x-y;
			return t;
	}
		
		public static double multiplicación(double x, double y){
			double result=0;
			for (int i = 0; i < y; i++) {
				 result=suma(result, x);	
			}
			return result;
		
			}
		
		public static double division (double x, double y){
				
			if (x!=0){
			double t=x/y;
					return t;
				}
				
				if (y==0){
					
					}
				return Double.NaN;

			}
		
		public static int modulo (int x, int y){
			int c= x%y;
			
			return c;

		}
		
		public static double potencia (double base, double exponente){
				if(exponente==1){
					return base;

				}
				else{
				if (exponente==0){
					return 1;
				}
				else{
				if (exponente<1){
					return (1/potencia(base, exponente*(-1)));
					
				}
				else{
					return base*potencia(base,exponente-1);
					
				}	
			}		
		}

	}
		

			public static int f_factorial(double d){
				if (d<1){
					return 1;
				}
				else {
					return (int)multiplicación(d, f_factorial(d-1));
				}
			}

			public static double signo(double rad){
				if (rad%2==0){
					return 1;
				}
					else {
						return -1;
					}
			}
			
			public static double sin(int x){
				int tope=10;
				double seno=0;
				double rad=Math.toRadians(x);
			for (int i = 0; i < tope; i++) {
				
			 seno += (signo(i)/f_factorial((2*i)+1))*potencia(rad,(2*i+1));	
			}
			
			return seno;
			}
			
			public static double cos(int x){
			int tope=10;
			double rad=Math.toRadians(x);
			double coseno=0;
			for (int n = 0; n < tope; n++) {
			coseno += (signo(n)/f_factorial(2*n))*potencia(rad,(2*n));	
		    }
			return coseno;

       }
			public static double integral(double inicio, double fin, double paso ){
				int acu=0;
			for (double i=inicio;i<fin; i+=paso){
				acu += (paso*potencia(i, 2));
		}
			return acu;
				}
			
			public static int[] f_cuadratica(int a, int b, int c){
				int [] fun=new int[2];
				    
			double disc=((b*b)-(4*(a*c)));
			if (disc>=0||a>0){
			 fun[0]=(int) (((-b)+Math.sqrt(disc))/(2*a));	
			 fun[1]=(int) (((-b)-Math.sqrt(disc))/(2*a));	
			}
			
			else{
			System.out.println("no se encuentra en los numeros reales");
			}
					
					
					return fun;		
			}		
		}
