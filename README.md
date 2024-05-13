# Criando-um-App-Flutter-do-Zero-Para-o-Consumo-da-API-do-ViaCEP

Vamos dividir o projeto em módulos para facilitar o entendimento e a implementação prática:

---

### **Módulo 1: Introdução ao Flutter e Configuração do Ambiente**
Antes de começar a codificar, é essencial configurar o ambiente de desenvolvimento. Instale o Flutter SDK e configure um editor de código, como o VS Code ou Android Studio. Certifique-se de que o `flutter doctor` não reporte problemas.

### **Módulo 2: Entendendo o Consumo de API**
APIs são fundamentais para a comunicação entre diferentes sistemas. No Flutter, utilizamos o pacote `http` para realizar requisições HTTP. Familiarize-se com os métodos `GET`, `POST`, `PUT`, e `DELETE`.

### **Módulo 3: Assincronismo em Dart**
O Dart utiliza `Future` e `async/await` para operações assíncronas. Pratique esses conceitos criando funções que simulam chamadas de rede com `Future.delayed`.

### **Módulo 4: Estruturando o App Flutter**
Crie um novo projeto Flutter e organize-o em pastas para modelos (`models`), serviços (`services`), telas (`screens`) e componentes (`widgets`). Mantenha o código limpo e modular.

### **Módulo 5: Implementando a API do ViaCEP**
Crie um serviço que consuma a API do ViaCEP. Use o método `GET` para buscar informações de CEPs. Trate os dados recebidos e exiba-os em uma tela.

### **Módulo 6: Construindo a Interface do Usuário**
Desenvolva a interface do usuário (UI) utilizando `Widgets`. Crie campos de entrada para o CEP e botões para realizar a busca. Mostre os resultados em um layout amigável.

### **Módulo 7: Testes e Depuração**
Escreva testes unitários para o seu serviço de API e utilize o debugger do Flutter para solucionar problemas. Garanta que sua aplicação esteja estável e confiável.

### **Módulo 8: Conclusão e Melhorias**
Após testar e depurar seu app, considere adicionar funcionalidades extras, como cache de dados ou uma UI mais interativa. Reflita sobre o que aprendeu e como pode aplicar isso em futuros projetos.

---

Aqui está um exemplo prático de como consumir a API do ViaCEP em Dart:

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';

Future<void> fetchCep(String cep) async {
  final response = await http.get(Uri.parse('https://viacep.com.br/ws/$cep/json/'));

  if (response.statusCode == 200) {
    final Map<String, dynamic> data = json.decode(response.body);
    print('CEP: ${data['cep']}');
    print('Logradouro: ${data['logradouro']}');
    // Adicione mais prints para os dados desejados
  } else {
    throw Exception('Falha ao carregar dados do CEP');
  }
}
```

Este código faz uma requisição `GET` para a API do ViaCEP e imprime alguns dos dados retornados. Lembre-se de tratar exceções e erros para garantir uma boa experiência do usuário.

Espero que este guia modular ajude você a criar seu app Flutter do zero para o consumo da API do ViaCEP!
