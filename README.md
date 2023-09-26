# calculadora_IMC.dart

Classe Pessoa 
class Pessoa {
  double peso;
  double altura;

  Pessoa(this.peso, this.altura);

  double calcularIMC() {
    return peso / (altura * altura);
  }

  void classificarIMC() {
    double imc = calcularIMC();

    if (imc < 18.5) {
      print("Você está abaixo do peso.");
    } else if (imc >= 18.5 && imc < 25) {
      print("Seu peso está dentro da faixa saudável.");
    } else if (imc >= 25 && imc < 30) {
      print("Você está com sobrepeso.");
    } else {
      print("Você está com obesidade.");
    }
  }
}

Calculo IMC 
import 'dart:io';
import 'package:calculo_imc/classpessoa.dart';

void main() {
  // Solicita ao usúario que insira seu peso em quilogramas
  print("Digite seu peso em quilogramas:");
  double peso = double.parse(stdin.readLineSync()!);

  // Solicita ao usúario que insira sua altura em metros
  print("Digite sua altura em metros:");
  double altura = double.parse(stdin.readLineSync()!);

  // Cria uma instância da classe Pessoa
  Pessoa pessoa = Pessoa(peso, altura);

  // Calcula e classifica o IMC
  pessoa.classificarIMC();
}
