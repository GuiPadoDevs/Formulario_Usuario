package usarformulariousuario;

import javax.swing.JOptionPane;

public class Usuario {
    private String identificacao;
    
    public Usuario(String identificacao){
        this.identificacao = identificacao;
        }
    
    public String getIdentificacao(){
        return identificacao;
        }
    
    public void validarUsuario(String id){ //Método para validar o usuário
        
        if (this.identificacao.equals(id)) { //Aqui ele verifica de o usuário é o mesmo já registrado
            JOptionPane.showMessageDialog(null, " Usuario " + this.identificacao + " autorizado! " );
        } else { //Se não for registrado ele consta como usuário desconhecido
                JOptionPane.showMessageDialog(null, " Usuario " + id + " desconhecido! " );
            }
        }
}
