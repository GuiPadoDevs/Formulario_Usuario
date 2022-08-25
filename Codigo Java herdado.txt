package usarformulariousuario;

import java.awt.*; 
import java.awt.event.ActionListener; 
import java.awt.event.ActionEvent; 
import javax.swing.JOptionPane;

public class FormularioUsuario extends Frame implements ActionListener{ 
//Aqui ele imprelenta a classe responsável pelas ações
    
    protected Dimension dQuadro, dRotulo, dCaixaTexto, dBotao;
    protected Button bValidar, bSair;
    protected TextField tfUsuario;
    protected Label lUsuario;
    
    Usuario alunoUm = new Usuario("Guilherme");
    
    public FormularioUsuario(){
        
        Dimension dQuadro = new Dimension(290,200);
        Dimension dRotulo = new Dimension(45,25);
        Dimension dCaixaTexto = new Dimension(180,25);
        Dimension dBotao = new Dimension(100,25);
        
        setTitle("Validar Usuario");
        setResizable(false);
        setSize(dQuadro);
        setLocation(650,350);
        setLayout(null);
        
        lUsuario = new Label("Usuário");
        lUsuario.setSize(dRotulo);
        lUsuario.setLocation(25,50);
        tfUsuario = new TextField();
        tfUsuario.setSize(dCaixaTexto);
        tfUsuario.setLocation(80,50);
        
        bValidar = new Button("Validar Usuário");
        bValidar.setSize(dBotao);
        bValidar.setLocation(25,150);
        bValidar.addActionListener(this);
        
        bSair = new Button("Sair");
        bSair.setSize(dBotao);
        bSair.setLocation(130,150);
        bSair.addActionListener(this);
        
        add(lUsuario);
        add(tfUsuario);
        add(bValidar);
        add(bSair);
    }
    public void actionPerformed(ActionEvent evento){ //Método responsável pelas ações do formulário
        
        if(evento.getSource() == bValidar){ 
            alunoUm.validarUsuario(tfUsuario.getText()); 
            //Ao clicar no botão Validar ele chama a validação na classe usuário
        } if (evento.getSource() == bSair){ 
            //Se o usuário clicou no sair ele fecha o programa e escreve no painel
            System.out.println("Fim do Aplicativo. Obrigado!");
            System.exit(0);
            }
    }
}
