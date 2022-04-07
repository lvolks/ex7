# ex7
package br.edu.up;

import br_edu_up.Aluno;
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ex7 {
	
	public static void main(String[] args) throws FileNotFoundException {
		
		File arquivo = new File("C:\\Users\\09361060937\\eclipse-workspace\\ex07\\src\\Alunos.csv");
		Scanner leitor = new Scanner(arquivo);
		leitor.nextLine();
		
		Aluno[] alunos = new Aluno[70];
		
		double menor = 11;
		double maior = 0;
		int aprovados = 0;
		int reprovados = 0;
		double soma = 0;
		int contador = 0;
		while(leitor.hasNext()) {
			
			String linha = leitor.nextLine();
			String[] dadosLinha = linha.split(";");
			String matricula = dadosLinha[0];
			String nome = dadosLinha[1];
			double nota = Double.parseDouble(dadosLinha[2]);
			
			Aluno novoAluno = new Aluno();
			novoAluno.matricula = matricula;
			novoAluno.nome = nome;
			novoAluno.nota = nota;
			
			alunos[contador] = novoAluno;

			contador++;
			
		}
		
		for (int i = 0; i < alunos.length; i++) {
		
		Aluno a = alunos[i];
			
		System.out.println("Matricula do aluno: " + a.matricula);
		System.out.println("Nome do aluno: " + a.nome);
		System.out.println("Nota do aluno: " + a.nota);
		
		if(a.nota>=6) {
			aprovados++;
		} else {
			reprovados++;
		}
		
		if(a.nota>maior) {
			maior = a.nota;
		}
		
		if(a.nota<=menor) {
			menor = a.nota;
		}
		
		soma = soma + a.nota;
		
		System.out.println();
		
		}
		
		System.out.println("Quantidade de alunos: " + contador);
		System.out.println();
		System.out.println("Alunos aprovados: " + aprovados);
		System.out.println();
		System.out.println("Alunos reprovados: " + reprovados);
		System.out.println();
		System.out.println("Maior nota: " + maior);
		System.out.println();
		System.out.println("Menor nota: " + menor);
		System.out.println();
		System.out.println("Média geral: " + soma/70);
		
		leitor.close();
	}
}

------------------------------------------------------------------------------------------------------------------------

package br_edu_up;

public class Aluno {
	
	public String nome;
	public String matricula;
	public double nota;

}
