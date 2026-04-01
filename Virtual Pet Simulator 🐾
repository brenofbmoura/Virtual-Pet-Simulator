class VirtualPet(val nome: String) {
    var nivelDeFome = 50
    var nivelFelicidade = 50
    var nivelCansaco = 50
    var nivelIdade = 1

    fun alimentar() {
        nivelDeFome -= 10
        println("$nome foi alimentado. O nível de fome diminuiu.")
    }

    fun brincar() {
        nivelFelicidade += 10
        println("$nome está brincando e se sentindo mais feliz.")
        nivelCansaco += 10
        println("$nome está mais feliz e sente mais cansado.")
    }

    fun descansar() {
        println("Por quantas horas você gostaria que $nome descansasse? (1 - 8 horas)")
        val resposta = readLine()?.toIntOrNull()
        if (resposta == null || resposta < 1 || resposta > 8) {
            println("Opção inválida! Digite um número entre 1 e 8.")
        } else {
            nivelCansaco -= resposta * 10
            println("$nome descansou $resposta hora(s). Nível de cansaço diminuiu!")
        }
    }

    fun verificarStatus() {
        println("Status atual de $nome:")
        println("Nível de fome: $nivelDeFome")
        println("Nível de felicidade: $nivelFelicidade")
        println("Nível de cansaço: $nivelCansaco")
        println("Idade: $nivelIdade")
    }

    fun passarTempo(): Boolean {
        nivelDeFome += 3
        println("$nome está ficando mais faminto com o passar do tempo.")
        nivelFelicidade -= 3
        println("$nome está se sentindo sozinho ao passar do tempo.")
        nivelCansaco += 10
        println("$nome está se sentindo mais cansado ao passar do tempo.")
        nivelIdade += 1

        return when {
            nivelCansaco >= 100  -> { println("Você perdeu! $nome morreu de cansaço. Seu irresponsável!!!"); false }
            nivelDeFome >= 100   -> { println("Você perdeu! $nome morreu de fome. Seu irresponsável!!!"); false }
            nivelFelicidade <= 0 -> { println("Você perdeu! $nome morreu de depressão. Seu irresponsável!!!"); false }
            nivelIdade >= 50     -> { println("Você ganhou! Parabéns por cuidar bem de $nome!"); false }
            else -> true
        }
    }
}  // ← fecha a classe VirtualPet

fun main() {
    println("Bem-vindo ao Simulador de Animal de Estimação Virtual!")
    println("Digite o nome do seu animal de estimação:")
    val nomePet = readLine() ?: ""
    val pet = VirtualPet(nomePet)

    while (true) {
        println("\nEscolha uma ação:")
        println("1. Alimentar $nomePet")
        println("2. Brincar com $nomePet")
        println("3. Fazer que $nomePet descanse")
        println("4. Verificar o status de $nomePet")
        println("5. Sair")

        val escolha = readLine()?.toIntOrNull() ?: continue

        when (escolha) {
            1 -> pet.alimentar()
            2 -> pet.brincar()
            3 -> pet.descansar()
            4 -> pet.verificarStatus()
            5 -> {
                println("Saindo do Simulador de Animal de Estimação Virtual. Adeus!")
                return
            }
            else -> println("Escolha inválida. Tente novamente.")
        }

        if (!pet.passarTempo()) return
    }
}
