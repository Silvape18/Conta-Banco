
//uma classe em java com alguns atributos e métodos;

    package Aaula;
    
    public class ContaBanco {

    public int numConta;
    protected String tipo;
    private String Dono;
    private float saldo;
    private boolean status;
    
    public void estadoAtual(){
        
        System.out.println("________________________________________");
        System.out.println("Conta: " +this.getNumConta());
        System.out.println("Tipo: " + this.getTipo());
        System.out.println("Dono: " + this.getDono());
        System.out.println("Saldo: " + this.getSaldo());
        System.out.println("Status: " + this.getStatus());
        System.out.println("__________________________________________");
    
    }
    
   
    public void ContaBanco() {
        this.saldo = 0;
        this.status = false;

    }

    public void abrirConta(String t) {
        this.setTipo(t);
        this.setStatus(true);
        if("CC".equals(t)){
            this.setSaldo(50);
        } else if ("CP".equals(t)) {
            this.setSaldo(150);
        }

    }

    public void fecharConta() {
        if(this.getSaldo()>0){
            System.out.println("A conta não pode ser fechada porque ainda tem saldo");
        } else if(this.getSaldo() <0){
            System.out.println("Conta não pode ser fechada pois tem debito");
        }else{
        this.setStatus(false);
            System.out.println("Conta fechada com sucesso");
        }

    }

    public void depositar(float v) {
        if(this.getStatus()){
        this.saldo = this.saldo + v;
        this.setSaldo(this.getSaldo() + v);
            System.out.println("Deposito realizado com sucesso " + this.getDono());
        
        }

    }

    public void sacar(float v) {
        if(this.getStatus()){
        if(this.getSaldo() >= v){
        this.setSaldo(this.getSaldo() -v);
            System.out.println("Saque realizado na conta de " + this.getDono());
        }else {
            System.out.println("Saldo insuficiente para saque");
        }
        } else{System.out.println("Imposivel sacar de uma conta fechada");}
        

    }

    public void pagarmensal() {
        int v = 0; 
        if("CC".equals(this.getTipo())){
        v =12;
        }else if("CP".equals(this.getTipo())){
        v=20;
        
        } if(this.getStatus()){
        this.setSaldo(this.getSaldo() - v);
        System.out.println("Mensalidade paga com sucesso por " + this.getDono());
        
        } else{System.out.println("Impossivel pagar uma conta fechada");
        
        }
    }

    //metodo especial 
    public int getNumConta() {
        return numConta;
    }

    public void setNumConta(int numConta) {
        this.numConta = numConta;
    }

    public String getTipo() {
        return tipo;
    }

    public void setTipo(String tipo) {
        this.tipo = tipo;
    }

    public String getDono() {
        return Dono;
    }

    public void setDono(String Dono) {
        this.Dono = Dono;
    }

    public float getSaldo() {
        return saldo;
    }

    public void setSaldo(float saldo) {
        this.saldo = saldo;
    }

    public boolean getStatus() {
        return status;
    }

    public void setStatus(boolean status) {
        this.status = status;
    }

 
    }
