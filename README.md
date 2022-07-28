# Calculo-de-vendas-e-comissao-codigo-Java

Considere o enunciado abaixo:

Faça um programa que receba o total de vendas de cada vendedor de uma loja e armazene-as em um vetor. Receba também o percentual de comissão a que cada vendedor tem direito e armazene-os em um outro vetor. Receba os nomes desses vendedores e armazene-os em um terceiro vetor. Existem apenas dez vendedores na loja. Calcule e mostre:

um relatório com os nomes dos vendedores e os valores a receber referentes à comissão;
o total das vendas de todos os vendedores;
o maior valor a receber e o nome de quem o receberá;
o menor valor a receber e o nome de quem o receberá.
Complete o programa abaixo de forma que o código implemente corretamente o problema acima (arraste e solte os trechos de código nos espaços em branco).



public class CalculaComissao {
	public static void main(String[] args) {
		double[] vendas = new double[10];
		[double[] percComissao = new double[10];]
		String[] nome = new String[10];
		
		// Leitura
		for(int cont = 0; cont < nome.length; cont++) {
			System.out.printf("-------------------------- VENDEDOR %02d --------------------------\n", cont+1);
			System.out.print("Nome: ");
			[nome[cont] = System.console().readLine();]
			System.out.print("Total de vendas: ");
			[vendas[cont] = Double.parseDouble(System.console().readLine());]
			System.out.print("Percentual de comissao: ");
			[percComissao[cont] = Double.parseDouble(System.console().readLine());]
		}
		
		// Mostra nomes dos vendedores e comissao a receber e efetua e efetua outros processamentos.
		[double totalVendas = 0;]
		double maiorComissao = 0;
		String nomeMaior = "";
		double menorComissao = 0;
		String nomeMenor = "";
		for(int cont = 0; cont < nome.length; cont++) {
			[double comissao = vendas[cont] * percComissao[cont] / 100;]
			System.out.printf("Vendedor %s deve receber comissao de R$ %.2f\n", nome[cont], comissao);
			
			totalVendas += vendas[cont];
			if(cont == 0 || comissao > maiorComissao) {
				maiorComissao = comissao;
				[nomeMaior = nome[cont];]
			}
			if(cont == 0 || comissao < menorComissao) {
				menorComissao = comissao;
				[nomeMenor = nome[cont];]
			}
		}
		
		System.out.printf("\nTOTAL DE VENDAS = R$ %.2f\n", totalVendas);
		System.out.printf("VENDEDOR COM MAIOR COMISSAO = %s (R$ %.2f)\n", nomeMaior, maiorComissao);
		System.out.printf("VENDEDOR COM MENOR COMISSAO = %s (R$ %.2f)\n", nomeMenor, menorComissao);
	}
}
