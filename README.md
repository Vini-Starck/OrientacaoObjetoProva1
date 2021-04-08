# OrientacaoObjetoProva1
Prova 1 de Orientação ao Objeto


public class Esteira {
    private String Teletrica;
    private int Vmax;
    private double Pmax;
    private String LD;
    private int Vatual;

    //Construtor
    public Esteira(String Tele,int Vmax,double Pmax){
        this.Teletrica = Tele;
        this.Vmax =  Vmax;
        this.Pmax =  Pmax;
        this.Vatual = 0;
        this.LD = "DESLIGADO";
    }
    
    public String getTeletrica() {
        return Teletrica;
    }

    public void setTeletrica(String Teletrica) {
        this.Teletrica = Teletrica;
    }
    public int getVmax() {
        return Vmax;
    }
    public void setVmax(int Vmax) {
        this.Vmax = Vmax;
    }

    public double getPmax() {
        return Pmax;
    }

    public void setPmax(double Pmax) {
        this.Pmax = Pmax;
    }

    public String getLD() {
        return LD;
    }

    public void setLD(String LD) {
        this.LD = LD;
    }

    public int getVatual() {
        return Vatual;
    }

    public void setVatual(int Vatual) {
            if(Vatual <= this.Vmax && Vatual > 0){
                this.Vatual = Vatual;
                
            }else{
                System.out.println("Excedeu a velocidade ou ela é insuficiente!");
                this.Vatual = 0;
            }
    }
    

    public void Estado(String estado){
        if(estado.equals("LIGADO")){
            this.LD = "LIGADO";
        }else if(estado.equals("DESLIGADO")){
            this.LD = "DESLIGADO";
        }else{
            System.out.println("Comando inválido!");
        }
    }
    
     public void beginE(int Vinicial,double peso){
         
     if(this.LD.equals("LIGADO")){ 
        if((Vinicial <= this.Vmax && peso <= this.Pmax) && (peso > 0 && Vinicial > 0 )){
            this.Vatual = Vinicial;
            System.out.println("TREINO INICIADO! RUN!");
        }else{
            System.out.println("OPS! RECOMENDO OLHAR O MANUAL!");
        }    
      }    
    }
    public String endE(){
        
        while(this.Vatual > 0){
            this.Vatual = this.Vatual -2;
            System.out.println("DIMINUINDO VELOCIDADE ATUAL:"+this.Vatual);
        }
        this.Vatual = 0;
        return "TREINO ENCERRADO!";
        
    }
    
}
