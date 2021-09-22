#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>
#include <time.h>

typedef struct{
  char nomeNavio[11];
  int tamanhoNavio;
  int IDNavio;
  int orientacaoNavio; 
  /*0 para vertical e 1 para horizontal*/
  char coordenadaLetra; // 'a' a 'j'
  int coordenadaNumero; //1 a 10
} tNavio;

tNavio LeNavio( FILE * tabu );

char* RetornaNomeNavio ( tNavio navio );

int RetornaOrientacaoNavio ( tNavio navio );

int RetornaTamanhoNavio ( tNavio navio );

int RetornaCoordenadaColunaInicioNavio ( tNavio navio );

char RetornaCoordenadaLinhaInicioNavio ( tNavio navio );

int RetornaIDNavio ( tNavio navio );

tNavio SalvaTamanhoNavio ( tNavio navio, int tamanho );


typedef struct{
  char jogadaString[10];
  int linha;
  int coluna;
} tJogada;

tJogada LeJogada();

int EhJogadaValida (tJogada jogada);

tJogada ConverteJogadaLidaEmInteiros ( tJogada jogada );

int RetornaLinhaJogada ( tJogada jogada );

int RetornaColunaJogada ( tJogada jogada );

char* RetornaJogadaEmString ( tJogada jogada );


typedef struct{
  int tirosAcertados;
  int tirosErrados;
  
  float SomaLocalizacoes[1][2];
  /*referente as somas das linhas 
  e das colunas das jogadas*/

  float desvioPadrao;
  float somatorioDesvioPadrao;
  int qtdJogadas;
  int qtdDeNaviosAcertados;
  
  int IDsNaviosAcertados[20][2];
  /*junto ai ID preciso salvar a jogada em
  que o navio foi atingido pela primeira vez*/

  tJogada jogadasValidas[100];
} tDados;

tDados ResetaQtdJogadas ( tDados dados );

tDados ResetaQtdNaviosAcertados ( tDados dados );

tDados ModificaIdDoNavioAcertado ( tDados dados, int posicao, int num );

int RetornaQtdJogadas( tDados dados);

tDados IncrementaQtdJogadas ( tDados dados );

tDados IncrementaQtdTirosAcertados ( tDados dados );

tDados IncrementaQtdTirosErrados ( tDados dados );

tDados IncrementaQtdNaviosAcertados ( tDados dados );

int RetornaQtdNaviosAcertados ( tDados dados );

int RetornaIdNaviosAcertados ( tDados dados, int posicao );

int RetornaJogadaNavioFoiAcertadoPrimeiraVez ( tDados dados, int posicao );

tDados SalvaJogada ( tDados dados, tJogada jogada, int numeroDaJogada);

tDados SalvaIdDoNavioAcertadoEJogada ( tDados dados, int posicao, int id , int jogada );

char* RetornaJogadaValidaEmString ( tDados dados, int posicao);

int RetornaLinhaJogadaValida ( tDados dados, int posicao);

int RetornaColunaJogadaValida ( tDados dados, int posicao);

int RetornaQtdTirosErrados ( tDados dados );

int RetornaQtdTirosAcertados( tDados dados );

tDados AtualizaSomaDasLocalizacoes ( tDados dados, int linha, int coluna );

float RetornaSomaLocalizacoesLinha ( tDados dados );

float RetornaSomaLocalizacoesColuna ( tDados dados );

tDados AtualizaSomatorioDesvioPadrao ( tDados dados, float num );

float RetornaSomatorioDesvioPadrao ( tDados dados );


typedef struct{
  int matriz[10][10][2];
  /*a matriz eh da forma: 
  [linha][coluna][condicoes]

  [condicoes] tem dois espacos:

  [condicoes] == [0] ira guardar se a 
  posicao eh agua ou navio

  [condicoes] == [1] ira guardar se a 
  posicao ja foi "aberta",
  isto é se o jogador adversario ja atirou
  naquela posicao
  
  se [linha][coluna][1] == 0
  a posicao esta fechada

  se [linha][coluna][1] == 1
  a posicao ja foi aberta*/
  
  int qtdNaviosTotal;
  int qtdNaviosCarrier;
  int qtdNaviosBattleship;
  int qtdNaviosCruiser;
  int qtdNaviosSubmarine;
  int qtdNaviosDestroyer;
  tNavio naviosDoTabuleiro[20]; 
  /*considerei que ha no maximo 20 navios em um 
  tabuleiro(esse numero ja excede o maximo possivel
  pelas minhas contas)*/
  tDados dadosJogadasAdversario;

} tTabuleiro;

int RetornaNumeroNaPosicaoDadaDaMatriz ( tTabuleiro tabuleiro, int linha, int coluna );

//condicao se refere a aberta/fechada
int RetornaCondicaoPosicaoDadaDaMatriz ( tTabuleiro tabuleiro, int linha, int coluna );

int RetornaQtdNaviosTotal ( tTabuleiro tabuleiro );

int RetornaQtdNaviosCarrier ( tTabuleiro tabuleiro );

int RetornaQtdNaviosBattleship ( tTabuleiro tabuleiro );

int RetornaQtdNaviosCruiser ( tTabuleiro tabuleiro );

int RetornaQtdNaviosSubmarine ( tTabuleiro tabuleiro );

int RetornaQtdNaviosDestroyer ( tTabuleiro tabuleiro );

tNavio RetornaNavioDoTabuleiro ( tTabuleiro tabuleiro, int posicao );

tDados RetornaDadosDasJogadasNoTabuleiro ( tTabuleiro tabuleiro );


int EhJogadaRepetida( tJogada jogada, tTabuleiro tabuleiro);

void ImprimeTabuleiroNoArquivo( tTabuleiro tabuleiro,
FILE * arquivo );

tTabuleiro LeTabuleiro( FILE * tabu );

tTabuleiro IniciaMatrizDoTabuleiro ( tTabuleiro tabuleiro );

int TemNavioSobreposto ( tTabuleiro tabuleiro );

int VerificaSeNaviosNaoExcedemABorda ( tTabuleiro tabuleiro );

int EhTabuleiroValido ( tTabuleiro tabuleiro );

int SaoTabuleirosCompativeis( tTabuleiro tabu_1, tTabuleiro tabu_2);

tTabuleiro FechaTodasPosicoes ( tTabuleiro tabuleiro );

int HaNaviosNaoAfundados ( tTabuleiro tabuleiro );

tTabuleiro DeixaPosicaoVisivel ( tTabuleiro tabuleiro, tJogada jogada );

int EhNavioAfundado ( tTabuleiro tabuleiro, int numeroNaPosicaoJogada );

tTabuleiro JogaJogada ( char nomeAdversario[], tJogada jogada, tTabuleiro tabuleiro,  FILE * arquivo );

tTabuleiro AtualizaDadosJogadasAdversario( tTabuleiro tabuleiro, tJogada jogada);

void ImprimeResumoDoResultadoNoArquivo ( tTabuleiro tabuleiroJogador1,   tTabuleiro tabuleiroJogador2, char nomeJogador1[], char nomeJogador2[], FILE * arquivo );

tTabuleiro OrdenaNaviosAcertadosEmOrdemCrescente( tTabuleiro tabuleiro );

void ImprimeEstatisticasNoArquivo( tTabuleiro tabuleiroJogador1,   tTabuleiro tabuleiroJogador2, char nomeJogador1[], char nomeJogador2[], FILE * arquivo );

//funcao que gera tabuleiro valido
void GeraTabuleiroValido ( FILE * arquivo, char* diretorio );

int main(int argc, char * argv[]) {
    FILE * tabu_1; 
    FILE * tabu_2;
    FILE * validacao_tabu;
    FILE * Arquivo_inicializacao;
    FILE * Arquivo_saidaJogadas;
    FILE * Arquivo_resultado;
    FILE * Arquivo_estatisticas;

    char diretorioTabu1[1001], 
    diretorioTabu2[1001], 
    enderecoSaida[1010], 
    enderecoValidacaoTabu[1040],
    enderecoInicializacao[1040], 
    enderecoSaidaJogadas[1040],
    enderecoResultado[1040],
    enderecoEstatisticas[1040],
    nomeJogador1[17], 
    nomeJogador2[17];

    int i, jogadaValidaNaoRepetida = 0;
    tTabuleiro tabuleiroJogador1, tabuleiroJogador2;
    tJogada jogada;
    

    //verificar a presença do diretorio com os arquivos
    if(  argc <= 1){
      printf("ERRO: O diretorio de arquivos de configuracao nao foi informado");
      return 0;
    }
    //O PROGRAMA NAO RECEBEU O '-GT', LOGO DEVERA JOGAR O JOGO
    else if ( argc == 2 ){
      //cria os diretorios com os nomes dos tabuleiros
      sprintf( diretorioTabu1 ,"%s/tabu_1.txt", argv[1]);
      sprintf( diretorioTabu2 ,"%s/tabu_2.txt", argv[1]);

      //abre os arquivos tabu_1 e tabu_2 para leitura
      tabu_1 = fopen( diretorioTabu1, "r");
      tabu_2 = fopen( diretorioTabu2, "r");

      if( !tabu_1 ){
          printf("Nao foi possivel ler o arquivo %s ! \n",
                diretorioTabu1 );
        return 1;
      }
      if( !tabu_2 ){
          printf("Nao foi possivel ler o arquivo %s ! \n",
                diretorioTabu2 );
        return 1;
      }

      //le os dois tabuleiros
      tabuleiroJogador1 = LeTabuleiro( tabu_1 );
      tabuleiroJogador2 = LeTabuleiro( tabu_2 );

      //cria o endereco de saida para o 
      //arquivo de validacao tabuleiro;
      /*feito em dois passos pois o endereco 
      de saida pode ser usado futuramente dessa forma;*/
      sprintf( enderecoSaida ,"%s/saida", argv[1]);
      sprintf( enderecoValidacaoTabu, 
      "%s/validacao_tabuleiros.txt", enderecoSaida);

      validacao_tabu = fopen( enderecoValidacaoTabu, "w");

      /*verifica a validade dos tabuleiros e salva o 
      resultado*/
      if( EhTabuleiroValido( tabuleiroJogador1 ) && 
          EhTabuleiroValido( tabuleiroJogador2 )){

        fprintf( validacao_tabu , "tabu_1.txt;valido\n");
        fprintf( validacao_tabu , "tabu_2.txt;valido\n");

        //cria os tabuleiros dos dois jogadores
        tabuleiroJogador1 = 
        IniciaMatrizDoTabuleiro( tabuleiroJogador1 );
        tabuleiroJogador2 = 
        IniciaMatrizDoTabuleiro( tabuleiroJogador2 );

        //verifica a compatibilidade dos tabuleiros
        if( SaoTabuleirosCompativeis( tabuleiroJogador1, tabuleiroJogador2 ))
          fprintf( validacao_tabu , "Tabuleiros compativeis entre si");
        else
          fprintf( validacao_tabu , "Tabuleiros incompativeis entre si");
      }
      else {
        if ( EhTabuleiroValido( tabuleiroJogador1 ) )
          fprintf( validacao_tabu , "tabu_1.txt;valido\n");
        else
          fprintf( validacao_tabu , "tabu_1.txt;invalido\n");
        
        if( EhTabuleiroValido( tabuleiroJogador2 ) )
          fprintf( validacao_tabu , "tabu_2.txt;valido");
        else
          fprintf( validacao_tabu , "tabu_2.txt;invalido");
      }
      fclose( validacao_tabu );

      //criar o arquivo de saida das jogadas
      sprintf( enderecoSaidaJogadas, 
      "%s/saida.txt", argv[1]);
      Arquivo_saidaJogadas = 
      fopen( enderecoSaidaJogadas, "w");


      /* se sao tabuleiros validos e compativeis
      podemos criar os arvios de saida das jogadas
      e de inicializacao, alem de receber o nome 
      dos jogadores*/
      if( EhTabuleiroValido( tabuleiroJogador1 ) && 
          EhTabuleiroValido( tabuleiroJogador2 ) &&
          SaoTabuleirosCompativeis( tabuleiroJogador1, 
                                    tabuleiroJogador2)){

        
        //recebe os nomes dos jogadores
        fprintf( Arquivo_saidaJogadas,"Nome do Jogador 1:\n");
        printf( "Nome do Jogador 1:\n");
        scanf("%s", nomeJogador1 );
        scanf("%*[^\n]");
        scanf("%*c");
        fprintf( Arquivo_saidaJogadas, "Nome do Jogador 2:\n");
        printf( "Nome do Jogador 2:\n");
        scanf("%s", nomeJogador2 );
        scanf("%*[^\n]");
        scanf("%*c");


        //cria endereco para salvar o arquivo de inicializacao
        //abre o arquivo e passa os dados
        sprintf( enderecoInicializacao, "%s/inicializacao.txt",
        enderecoSaida);
        Arquivo_inicializacao = 
        fopen( enderecoInicializacao ,"w");

        fprintf( Arquivo_inicializacao , 
        "%s\n", nomeJogador1 );

        ImprimeTabuleiroNoArquivo ( tabuleiroJogador1,
                                    Arquivo_inicializacao );
        fprintf( Arquivo_inicializacao , "\n\n");

        fprintf( Arquivo_inicializacao , 
        "%s\n", nomeJogador2 );
        ImprimeTabuleiroNoArquivo ( tabuleiroJogador2, 
                                    Arquivo_inicializacao );
        
        fclose( Arquivo_inicializacao );
      }


      /*uma vez o aquivo de saida foi criado e os nomes
      dos jogadores recebidos podemos iniciar o jogo
      se os tabuleiros sao validos e compativeis,
      entao podemos comecar a ler as jogadas*/
      if( EhTabuleiroValido( tabuleiroJogador1 ) && 
          EhTabuleiroValido( tabuleiroJogador2 ) &&
          SaoTabuleirosCompativeis( tabuleiroJogador1, 
                                    tabuleiroJogador2)){


        /*fechar (esconder) todas posicoes dos dois 
        tabuleiro antes de comecar o jogo*/
        tabuleiroJogador1 = 
        FechaTodasPosicoes( tabuleiroJogador1 );
        tabuleiroJogador2 = 
        FechaTodasPosicoes( tabuleiroJogador2 );


        /*enquanto houver navios nao afundados em ambos
        os tabuleiros deve continuar lendo as jogadas*/
        while ( HaNaviosNaoAfundados( tabuleiroJogador1 ) &&
                HaNaviosNaoAfundados( tabuleiroJogador2 )){
          
          //JOGADA DO JOGADOR 1
          fprintf( Arquivo_saidaJogadas, "\nJogada de %s:\n", nomeJogador1);

          jogadaValidaNaoRepetida = 0;

          //ler a jogada do jogador 1:
          /*enquanto nao for jogada valida continuar
          "pedindo" jogadas*/
          while ( !jogadaValidaNaoRepetida ){
            jogada = LeJogada();
            
            /*le a jogada como string e essa funcao 
            converte a jogada para inteiros para que
            as operacoes com esses valores seja mais facil*/ 
            jogada = ConverteJogadaLidaEmInteiros( jogada );


            /*se for jogada valida e n repetida pode fazer
            a jogada*/
            if ( EhJogadaValida ( jogada ) &&
                !EhJogadaRepetida( jogada, tabuleiroJogador2 )){

                /*guarda as informacoes sobre os tiros e as
                jogadas em si;
                IMPORTANTE:
                Os dados das jogadas do jogador eh salvo no
                tabuleiro do adversario, uma vez que o 
                adversario joga em cima do tabuleiro desse 
                jogador*/
                tabuleiroJogador2 = 
                AtualizaDadosJogadasAdversario ( tabuleiroJogador2, jogada);

                tabuleiroJogador2 = 
                JogaJogada ( nomeJogador2, jogada, tabuleiroJogador2, Arquivo_saidaJogadas );

                fprintf( Arquivo_saidaJogadas, "\nTabuleiro atual de %s apos a jogada de %s\n", 
                nomeJogador2 , nomeJogador1);

                ImprimeTabuleiroNoArquivo ( tabuleiroJogador2, Arquivo_saidaJogadas );
                fprintf( Arquivo_saidaJogadas, "\n" );


                jogadaValidaNaoRepetida = 1;
            }
            //se nao for valida ou repetida solicitar nova
            //jogada
            else{
                fprintf( Arquivo_saidaJogadas, "\n%s:Jogada invalida! Jogue novamente %s:\n",
                RetornaJogadaEmString( jogada ), nomeJogador1);
            }
          }

          //VEZ DO JOGADOR 2
          fprintf( Arquivo_saidaJogadas, "\nJogada de %s:\n", nomeJogador2 );

          jogadaValidaNaoRepetida = 0;
          //ler a jogada do jogador 2:
          //enquanto nao for jogada valida continuar "pedindo" jogadas
          while ( !jogadaValidaNaoRepetida ){
            jogada = LeJogada();
            jogada = ConverteJogadaLidaEmInteiros( jogada );

            if ( EhJogadaValida ( jogada ) &&
                !EhJogadaRepetida( jogada, tabuleiroJogador1 )){

                //guarda a quantidade de tiros e as jogadas em si
                tabuleiroJogador1 = 
                AtualizaDadosJogadasAdversario( tabuleiroJogador1, jogada);
                
                tabuleiroJogador1 = 
                JogaJogada ( nomeJogador1, jogada, tabuleiroJogador1, Arquivo_saidaJogadas );

                fprintf( Arquivo_saidaJogadas, "\nTabuleiro atual de %s apos a jogada de %s\n", 
                nomeJogador1 , nomeJogador2 );

                ImprimeTabuleiroNoArquivo ( tabuleiroJogador1, Arquivo_saidaJogadas );
                fprintf( Arquivo_saidaJogadas, "\n" );

                jogadaValidaNaoRepetida = 1;
            }
            else{
                fprintf( Arquivo_saidaJogadas, "\n%s:Jogada invalida! Jogue novamente %s:\n", 
                RetornaJogadaEmString( jogada ), nomeJogador2);
            }
          }
        }
        //ACABOU O JOGO
        /*quando sair do while acima eh pq alguem 
        venceu ou empatou, afinal ha pelo menos um tabuleiro
        em que nao ha mais navios nao afundados*/
        //se isso ocorreu nos dois eh empate

        /*cria o endereco de saida para o 
        arquivo de resultado;*/
        sprintf( enderecoResultado, 
        "%s/resultado.txt", enderecoSaida);
        Arquivo_resultado = fopen( enderecoResultado, "w");

        //imprime o resumo no seu devido arquivo
        ImprimeResumoDoResultadoNoArquivo ( tabuleiroJogador1, tabuleiroJogador2,
        nomeJogador1, nomeJogador2, Arquivo_resultado );

        /*verifica em qual(is) dos tabuleiros nao ha mais
        navios nao afundados para ver quem ganhou o jogo, e 
        imprime o resultado tanto no arquivo de saida
        quanto no arquivo de resumo do resultado*/
        if( !HaNaviosNaoAfundados( tabuleiroJogador1 )) {
          if( !HaNaviosNaoAfundados( tabuleiroJogador2 )){
            fprintf( Arquivo_saidaJogadas, "\nEmpate\n" );
            fprintf( Arquivo_resultado, "\nEmpate" );
          }
          else{
            fprintf( Arquivo_saidaJogadas, "\nVencedor: %s\n", nomeJogador2 );
            fprintf( Arquivo_resultado, "\nVencedor: %s", nomeJogador2 );
          }  
        }
        else{
          fprintf( Arquivo_saidaJogadas, "\nVencedor: %s\n", nomeJogador1 );
          fprintf( Arquivo_resultado, "\nVencedor: %s", nomeJogador1 );
        }
        fclose( Arquivo_resultado );


        //gerar o arquivo das estatisticas
        sprintf( enderecoEstatisticas, 
        "%s/estatisticas.txt", enderecoSaida);
        Arquivo_estatisticas = fopen( enderecoEstatisticas, "w");

        ImprimeEstatisticasNoArquivo(  tabuleiroJogador1, tabuleiroJogador2,
        nomeJogador1, nomeJogador2, Arquivo_estatisticas );

        fclose( Arquivo_estatisticas );
      }
      
      fclose( Arquivo_saidaJogadas );

      fclose( tabu_1 );
      fclose( tabu_2 );
    }

    /*VERIFICAR SE REALMENTE O '-gt' FOI PASSADO COMO PARAMETRO, 
    SE SIM, DEVE-SE GERAR UM TABULEIRO VALIDO*/
    else if( (argc == 3) && ( strcmp(argv[1], "-gt") == 0) ){

      FILE * arquivo_tabuleiro;

      arquivo_tabuleiro = fopen( argv[2], "w");

      GeraTabuleiroValido ( arquivo_tabuleiro, argv[2] );
      
      fclose( arquivo_tabuleiro );
    }
    //houve erro ao informar o diretorio
    else{
      printf("ERRO: O diretorio de arquivos de configuracao nao foi informado corretamente!!!");
    }
  return 0;
}


// funcoes tNavio
tNavio LeNavio( FILE * tabu ){
  tNavio navio;
  int i;
  char a;

  fscanf( tabu, "%[^;]", navio.nomeNavio);
  fscanf( tabu, ";");
  fscanf( tabu, "%d", &navio.IDNavio);
  fscanf( tabu, ";");
  fscanf( tabu, "%d", &navio.orientacaoNavio);
  fscanf( tabu, ";");
  fscanf( tabu, "%c", &navio.coordenadaLetra);
  fscanf( tabu, "%d", &navio.coordenadaNumero);
  fscanf( tabu, "%*c");

  return navio;
}

char* RetornaNomeNavio ( tNavio navio ){
  char* nome;
  nome = navio.nomeNavio;
  return nome;
}

tNavio SalvaTamanhoNavio ( tNavio navio, int tamanho ){
  navio.tamanhoNavio = tamanho;
  return navio;
}

int RetornaOrientacaoNavio ( tNavio navio ){
  return navio.orientacaoNavio;
}

int RetornaTamanhoNavio ( tNavio navio ){
  return navio.tamanhoNavio;
}

int RetornaCoordenadaColunaInicioNavio ( tNavio navio ){
  return navio.coordenadaNumero;
}

char RetornaCoordenadaLinhaInicioNavio ( tNavio navio ){
  return navio.coordenadaLetra;
}

int RetornaIDNavio ( tNavio navio ){
  return navio.IDNavio;
}


//funcoes tJogada
tJogada LeJogada(){
  tJogada jogada;

  scanf("%s", jogada.jogadaString );
  scanf("%*[^\n]");
  scanf("%*c");

  return jogada;
}


int EhJogadaValida ( tJogada jogada ){

  if( jogada.jogadaString[0] >= 'a' &&
      jogada.jogadaString[0] <= 'j' &&
      jogada.jogadaString[1] >= '1' &&
      jogada.jogadaString[1] <= '9'){

      //jogadas do tipo @10
      if( jogada.jogadaString[1] == '1' &&
          jogada.jogadaString[2] == '0' &&
          jogada.jogadaString[3] == '\0'){
            jogada.coluna = 10;
            return 1;
      }
      else if ( jogada.jogadaString[2] == '\0' ){
        return 1;
      }
  }
  
  return 0;
}

tJogada ConverteJogadaLidaEmInteiros ( tJogada jogada ){

  if ( EhJogadaValida( jogada )){
    /*transforma a linha em forma de letra
    em um seu numero correspondente*/
    if( jogada.jogadaString[0] == 'a')
      jogada.linha = 1;
    else if( jogada.jogadaString[0] == 'b')
      jogada.linha = 2;
    else if( jogada.jogadaString[0] == 'c')
      jogada.linha = 3;
    else if( jogada.jogadaString[0] == 'd')
      jogada.linha = 4;
    else if( jogada.jogadaString[0] == 'e')
      jogada.linha = 5;
    else if( jogada.jogadaString[0] == 'f')
      jogada.linha = 6;
    else if( jogada.jogadaString[0] == 'g')
      jogada.linha = 7;
    else if( jogada.jogadaString[0] == 'h')
      jogada.linha = 8;
    else if( jogada.jogadaString[0] == 'i')
      jogada.linha = 9;
    else if( jogada.jogadaString[0] == 'j')
      jogada.linha = 10;

    /*transforma a coluna em forma de caractere
    em um seu numero correspondente*/

    //se for a coluna 10
    if( jogada.jogadaString[1] == '1' &&
        jogada.jogadaString[2] == '0' ){
          jogada.coluna = 10;
    }
    else{
      if( jogada.jogadaString[1] == '1')
        jogada.coluna = 1;
      else if( jogada.jogadaString[1] == '2')
        jogada.coluna = 2;
      else if( jogada.jogadaString[1] == '3')
        jogada.coluna = 3;
      else if( jogada.jogadaString[1] == '4')
        jogada.coluna = 4;
      else if( jogada.jogadaString[1] == '5')
        jogada.coluna = 5;
      else if( jogada.jogadaString[1] == '6')
        jogada.coluna = 6;
      else if( jogada.jogadaString[1] == '7')
        jogada.coluna = 7;
      else if( jogada.jogadaString[1] == '8')
        jogada.coluna = 8;
      else if( jogada.jogadaString[1] == '9')
        jogada.coluna = 9;
    }
  }

  return jogada;
} 

int RetornaLinhaJogada ( tJogada jogada ){
  return jogada.linha;
}

int RetornaColunaJogada ( tJogada jogada ){
  return jogada.coluna;
}

char* RetornaJogadaEmString ( tJogada jogada ){
  char* nome;
  nome = jogada.jogadaString;
  return nome;
}


//funcoes tDados
tDados ResetaQtdJogadas ( tDados dados ){
  dados.qtdJogadas = 0;
  return dados;
}

tDados ResetaQtdNaviosAcertados ( tDados dados ){
  dados.qtdDeNaviosAcertados = 0;
  return dados;
}

tDados ModificaIdDoNavioAcertado ( tDados dados, int posicao, int num ){
  dados.IDsNaviosAcertados[posicao][0] = num;
  return dados;
}

int RetornaQtdJogadas( tDados dados){
  int i;
  i = dados.qtdJogadas;
  return i;
}

tDados IncrementaQtdJogadas ( tDados dados ){
  dados.qtdJogadas++;
  return dados;
}

tDados IncrementaQtdTirosAcertados ( tDados dados ){
  dados.tirosAcertados++;
  return dados;
}

tDados IncrementaQtdTirosErrados ( tDados dados ){
  dados.tirosErrados++;
  return dados;
}

tDados IncrementaQtdNaviosAcertados ( tDados dados ){
  dados.qtdDeNaviosAcertados++;
  return dados;
}

int RetornaQtdNaviosAcertados ( tDados dados ){
  return dados.qtdDeNaviosAcertados;
}

int RetornaIdNaviosAcertados ( tDados dados, int posicao ){
  return dados.IDsNaviosAcertados[posicao][0];
}

int RetornaJogadaNavioFoiAcertadoPrimeiraVez ( tDados dados, int posicao ){
  return dados.IDsNaviosAcertados[posicao][1];
}

tDados SalvaJogada ( tDados dados, tJogada jogada, int numeroDaJogada){
  dados.jogadasValidas[numeroDaJogada-1] = jogada;
  return dados;
}

tDados SalvaIdDoNavioAcertadoEJogada ( tDados dados, int posicao, int id , int jogada ){
  dados.IDsNaviosAcertados[posicao][0] = id;
  dados.IDsNaviosAcertados[posicao][1] = jogada;
  /*salva a jogada em que o navio foi acertado 
  pela primeira vez*/
  return dados;
}

char* RetornaJogadaValidaEmString ( tDados dados, int posicao){
  char* nome;
  nome = RetornaJogadaEmString ( dados.jogadasValidas[posicao] );
  return nome;
}

int RetornaLinhaJogadaValida ( tDados dados, int posicao){
  int linha;
  linha = RetornaLinhaJogada ( dados.jogadasValidas[posicao] );
  return linha;
}

int RetornaColunaJogadaValida ( tDados dados, int posicao){
  int coluna;
  coluna = RetornaColunaJogada ( dados.jogadasValidas[posicao] );
  return coluna;
}

int RetornaQtdTirosErrados ( tDados dados ){
  return dados.tirosErrados;
}

int RetornaQtdTirosAcertados( tDados dados ){
  return dados.tirosAcertados;
}

tDados AtualizaSomaDasLocalizacoes ( tDados dados, int linha, int coluna ){
  //[0][0] eh a soma das linhas, [0][1] eh a soma das colunas
  dados.SomaLocalizacoes[0][0] += linha;
  dados.SomaLocalizacoes[0][1] += coluna;
  return dados;
}

float RetornaSomaLocalizacoesLinha ( tDados dados ){
  return dados.SomaLocalizacoes[0][0];
}

float RetornaSomaLocalizacoesColuna ( tDados dados ){
  return dados.SomaLocalizacoes[0][1];
}

tDados AtualizaSomatorioDesvioPadrao ( tDados dados, float num ){
  dados.somatorioDesvioPadrao += num;
  return dados;
}

float RetornaSomatorioDesvioPadrao ( tDados dados ){
  return dados.somatorioDesvioPadrao;
}



//funcoes tTabuleiro
int RetornaNumeroNaPosicaoDadaDaMatriz ( tTabuleiro tabuleiro, int linha, int coluna ){
  return tabuleiro.matriz[linha][coluna][0];
}

int RetornaCondicaoPosicaoDadaDaMatriz ( tTabuleiro tabuleiro, int linha, int coluna ){
  return tabuleiro.matriz[linha][coluna][1];
}

int RetornaQtdNaviosTotal (tTabuleiro tabuleiro ){
  return tabuleiro.qtdNaviosTotal;
}

int RetornaQtdNaviosCarrier ( tTabuleiro tabuleiro ){
  return tabuleiro.qtdNaviosCarrier;
}

int RetornaQtdNaviosBattleship ( tTabuleiro tabuleiro ){
  return tabuleiro.qtdNaviosBattleship;
}

int RetornaQtdNaviosCruiser ( tTabuleiro tabuleiro ){
  return tabuleiro.qtdNaviosCruiser;
}

int RetornaQtdNaviosSubmarine ( tTabuleiro tabuleiro ){
  return tabuleiro.qtdNaviosSubmarine;
}

int RetornaQtdNaviosDestroyer ( tTabuleiro tabuleiro ){
  return tabuleiro.qtdNaviosDestroyer;
}

tNavio RetornaNavioDoTabuleiro ( tTabuleiro tabuleiro, int posicao ){
  return tabuleiro.naviosDoTabuleiro[posicao];
}

tDados RetornaDadosDasJogadasNoTabuleiro ( tTabuleiro tabuleiro ){
  return tabuleiro.dadosJogadasAdversario;
}

tTabuleiro IncrementaQtdNaviosDeCadaTipo ( tTabuleiro tabuleiro, char* nomeNavio ){
  if( strcmp( nomeNavio, "Carrier") == 0)
      tabuleiro.qtdNaviosCarrier++;
  else if ( strcmp( nomeNavio, "Battleship") == 0)
      tabuleiro.qtdNaviosBattleship++;
  else if ( strcmp( nomeNavio, "Cruiser") == 0)
      tabuleiro.qtdNaviosCruiser++;
  else if ( strcmp( nomeNavio, "Submarine") == 0)
      tabuleiro.qtdNaviosSubmarine++;
  else if ( strcmp( nomeNavio,
     "Destroyer") == 0)
      tabuleiro.qtdNaviosDestroyer++;

  return tabuleiro;
}


tTabuleiro LeTabuleiro( FILE * tabu ){
  tTabuleiro tabuleiro;
  tNavio navio;
  int i = 0;

  tabuleiro.qtdNaviosCarrier = 0;
  tabuleiro.qtdNaviosBattleship = 0;
  tabuleiro.qtdNaviosCruiser = 0;
  tabuleiro.qtdNaviosSubmarine = 0;
  tabuleiro.qtdNaviosDestroyer = 0;

  while( 1 ){

    //trata os casos em que ha quebra de linha no final
    //e termina quando acha o final do arquivo
    fscanf( tabu, "%*c");
    if(!feof( tabu ))
      fseek( tabu, -1, SEEK_CUR);
    else break;

    tabuleiro.naviosDoTabuleiro[i] = LeNavio( tabu );

    /*salva quantos navios de cada tipo tem 
    e seus tamanhos no tabuleiro usado para 
    futuras comparacoes entre tabuleiros validos*/
    if( strcmp( RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, i) ),
     "Carrier") == 0){
      tabuleiro = IncrementaQtdNaviosDeCadaTipo( tabuleiro , "Carrier" );
      tabuleiro.naviosDoTabuleiro[i] = 
      SalvaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i), 5 );
    }
    else if ( strcmp( RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, i) ), 
     "Battleship") == 0){
      tabuleiro = IncrementaQtdNaviosDeCadaTipo( tabuleiro , "Battleship" );
      tabuleiro.naviosDoTabuleiro[i] = 
      SalvaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i), 4 );
    }
    else if ( strcmp( RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, i) ),
     "Cruiser") == 0){
      tabuleiro = IncrementaQtdNaviosDeCadaTipo( tabuleiro , "Cruiser" );
      tabuleiro.naviosDoTabuleiro[i] = 
      SalvaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i), 3 );
    }
    else if ( strcmp( RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, i) ),
     "Submarine") == 0){
      tabuleiro = IncrementaQtdNaviosDeCadaTipo( tabuleiro , "Submarine" );
      tabuleiro.naviosDoTabuleiro[i] = 
      SalvaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i), 3 );
    }
    else if ( strcmp( RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, i) ),
     "Destroyer") == 0){
      tabuleiro = IncrementaQtdNaviosDeCadaTipo( tabuleiro , "Destroyer" );
      tabuleiro.naviosDoTabuleiro[i] = 
      SalvaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i), 2 );
    }

    i++;
  }
  tabuleiro.qtdNaviosTotal = i;

  return tabuleiro;
}

void ImprimeTabuleiroNoArquivo ( tTabuleiro tabuleiro, FILE * arquivo ){
  int i, j;

  for( i = 0; i < 10; i++){
    for( j = 0; j < 10; j++){

      /*se for 0 eh agua, ou seja, imprimir 0,
      se nao, eh posicao ocupada por navio, imprimir 'X'*/
      // mesma coisa q se fizesse tabuleiro.matriz[i][j][0/1]
      if ( RetornaCondicaoPosicaoDadaDaMatriz( tabuleiro, i, j ) == 1 ){//se a posicao esta aberta
        if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j) == 0 )
          fprintf( arquivo ,"o");
        else
          fprintf( arquivo ,"X");
      }
      else{//posicao fechada
        fprintf( arquivo ,".");
      }

      if( j != 9)
        fprintf( arquivo , " ");
    }
    if( i != 9)
      fprintf( arquivo , "\n");
  }
}

tTabuleiro IniciaMatrizDoTabuleiro ( tTabuleiro tabuleiro ){
  int i, j, k, tamanho, qtdNavios, orientacao,
  linhaInicio, colunaInicio;
  qtdNavios = RetornaQtdNaviosTotal( tabuleiro );

  //inicia o numero de tiros do adversario com 0
  tabuleiro.dadosJogadasAdversario = 
  ResetaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));
  tabuleiro.dadosJogadasAdversario = 
  ResetaQtdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));

  //tbm iniciar os ids dos navios acertados com -1
  for(i = 0; i < 20; i++){
    tabuleiro.dadosJogadasAdversario = 
    ModificaIdDoNavioAcertado( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), i, -1);
  }

  /*inicializar todos os espacos com 0 
  (que respresentarao agua) inicialmente,
  os IDs de cada navio (num) representarao
  os espacos ocupados pelas embarcacoes*/
  for(i = 0; i < 10; i++){
    for( j = 0; j < 10; j++){
      tabuleiro.matriz[i][j][0] = 0 ; //navio/agua
      //iniciar com todas posicoes abertas (1)
      //para gerar o arquivo de inicializacao
      tabuleiro.matriz[i][j][1] = 1 ; //aberto/fechado
    }
  }

  for( i = 0; i < qtdNavios; i++){
    
    orientacao = 
    RetornaOrientacaoNavio ( RetornaNavioDoTabuleiro( tabuleiro, i ));
    tamanho = 
    RetornaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i ));
    colunaInicio = 
    RetornaCoordenadaColunaInicioNavio( RetornaNavioDoTabuleiro( tabuleiro, i ));
    //transforma a letra da coordenada vertical no seu numero correspondente
    // 'a' equivale a 1, 'b' equivale a 2, e assim ate 'j' == 10
    linhaInicio = 
    RetornaCoordenadaLinhaInicioNavio( RetornaNavioDoTabuleiro( tabuleiro, i )) -'a'+ 1;
    
    //demaracar na matriz o espaco ocupado pela embarcacao
    //a orientacao do navio eh 0 para vertical e 1 para horizontal
    if (orientacao == 0){
      k = 1;
      for( j = linhaInicio - 1; k <= tamanho; j++){

      /* inves de colocar 'X' diretamente p/ posicoes
      ocupadas por navios, optei por colocar o num do ID
      do navio;
      Dessa forma consigo ver o ID do navio em cada posicao,
      para necessidades futuras*/
        tabuleiro.matriz[j][colunaInicio-1][0] = 
        RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiro, i ));
        k++;
      }
    }
    else{ // ou seja, a orientacao eh 1 (horizontal)
      k = 1;
      for( j = colunaInicio - 1; k <= tamanho; j++){
        tabuleiro.matriz[linhaInicio-1][j][0] = 
        RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiro, i ));
        k++;
      }
    }
  }

  return tabuleiro;
}


int VerificaSeNaviosNaoExcedemABorda ( tTabuleiro tabuleiro ){
  int i, j, tamanho, qtdNavios, orientacao, linhaInicio, colunaInicio;
  qtdNavios = tabuleiro.qtdNaviosTotal;

  //verificar se os navios estao contidos na matriz
  for( i = 0; i < qtdNavios; i++){
    
    orientacao = 
    RetornaOrientacaoNavio ( RetornaNavioDoTabuleiro( tabuleiro, i ) );
    tamanho = 
    RetornaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i ) );
    colunaInicio = 
    RetornaCoordenadaColunaInicioNavio( RetornaNavioDoTabuleiro( tabuleiro, i ));
    //transforma a letra da coordenada vertical no seu numero correspondente
    // 'a' equivale a 1, 'b' equivale a 2, e assim ate 'j' == 10
    linhaInicio = 
    RetornaCoordenadaLinhaInicioNavio( RetornaNavioDoTabuleiro( tabuleiro, i )) -'a'+ 1;

    //se os navios estiverem fora do tabuleiro excede a borda
    if( linhaInicio < 1 || 
        linhaInicio > 10 ||
        colunaInicio < 1 || 
        colunaInicio > 10){
      return 0;
    }
    
    //a orientacao do navio eh 0 para vertical e 1 para horizontal
    if (orientacao == 0){
      //o '-1' se da pq ele comeca naquela propria linha de inicio
      if ( (linhaInicio - 1 + tamanho) > 10 ){
        return 0;
      }
    }
    else{ // ou seja, a orientacao eh 1 (horizontal)
      if ( (colunaInicio - 1 + tamanho) > 10 ){
        return 0;
      }
    }
  }

  return 1;
}


int TemNavioSobreposto ( tTabuleiro tabuleiro ){
  int i, j, posicoesComX = 0, espacoOcupadoNavios = 0,
  qtdNavios;
  qtdNavios = RetornaQtdNaviosTotal( tabuleiro);

  //conta quantos posicoes ocupadas por navios 
  // ha no tabuleiro
  for( i = 0; i < 10; i++){
    for( j = 0; j < 10; j++){
      if ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j) != 0 ){
        posicoesComX++;
      }
    }
  }

  //soma os espacos que os navios deveriam ocupar
  //no tabuleiro
  for(i = 0; i < qtdNavios; i++){
    espacoOcupadoNavios += 
    RetornaTamanhoNavio( RetornaNavioDoTabuleiro( tabuleiro, i ));
  }

  //se forem diferentes eh pq ha navios 
  //sobrepostos ou repetidos
  if( posicoesComX != espacoOcupadoNavios )
    return 1;
  else
    return 0;
}


int EhTabuleiroValido ( tTabuleiro tabuleiro ){
  int i, j, k, sequenciaHorizontalX = 0,
  sequenciaVerticalX = 0, maiorSequenciaX = 0;

  if( VerificaSeNaviosNaoExcedemABorda( tabuleiro ) ){
    tabuleiro = IniciaMatrizDoTabuleiro( tabuleiro );
  }
  else{
    return 0;
  }

  if( TemNavioSobreposto( tabuleiro ) ){
    return 0;
  }
    

  //verificar se os navios nao encostam nos outros
  /*dois navios so estaram encostados se ao verificar uma
  posicao na matriz em que esteja um "num" 
  ("num" representa o ID do navio)
  , estiver ao mesmo tempo um "num", acima ou abaixo dele, 
  e tambem um "num", a direita ou a esquerda desse "num" inicial,
  ou ainda se existirem quinas de navios encostando*/
  for( i = 0; i < 10; i++){
    sequenciaHorizontalX = 0;
    for( j = 0; j < 10; j++){
      sequenciaVerticalX = 0;
      if ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j) != 0){

        /* verificar se ha mais de cinco "num" em sequecia
        na horizontal, oq inidicara que ha navios
        encostados */
          sequenciaHorizontalX++;
          for( k = j+1; k < 10; k++){

            //ser for != 0, entao eh um "num"
            if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, k) != 0 )
              sequenciaHorizontalX++;
            else{
              if( sequenciaHorizontalX > maiorSequenciaX )
                maiorSequenciaX = sequenciaHorizontalX;
              sequenciaHorizontalX = 0;
              break;
            }
          }

        /* verificar se ha mais de cinco "num" em sequecia
        na vertical, oq inidicara que ha navios
        encostados */
          sequenciaVerticalX++;
          for( k = i+1; k < 10; k++){

            //ser for != 0, entao eh um "num"
            if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, k, j) != 0 )
              sequenciaVerticalX++;
            else{
              if( sequenciaVerticalX > maiorSequenciaX  )
                maiorSequenciaX = sequenciaVerticalX;
              sequenciaVerticalX = 0;
              break;
            }
          }
          


        //dividiremos o teste em dois casos
        //"num" esta na borda, ou
        //"num" nao esta na borda

        //verificar se o "num" esta na borda da matriz
        //se sim verificar se ha navios encostados
        if( i == 0 || j == 0 || i == 9 || j == 9){

          //  "num" esta na primeira linha
          if( i == 0 ){
            if ( j == 0 ){
              //novamente, ser for != 0, entao eh um "num"
              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j) != 0 &&  
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j+1) != 0){
                    return 0;
              }
            }
            else if ( j == 9 ){
              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j) != 0 &&  
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j-1) != 0){
                    return 0;
              }
            }
            else{
              /*aqui verificar se dois navios encostam
              suas quinas, nos casos acima nao faz sentido
              fazer essa verificacao pois todos navios
              tem tamanho maior ou igual a 2, entao esses
              casos ja teriam sido verificado pelas
              condicoes ja dadas, logo nao eh necessario
              verificar as quinas do tabuleiro nesse 
              caso*/

              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j) != 0 &&
                  ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j-1) != 0 || 
                    RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j+1) != 0) ){
                  return 0;
              }

              //verificar se quinas encostam nos casos i=0,
              //mas 0<j<9
              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j-1) != 0 ||
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j+1) != 0 ){
                    return 0;
              }
            }
          }
          
          //  "num" esta na ultima linha
          if( i == 9 ){
            if ( j == 0 ){
              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j) != 0 && 
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j+1) != 0 ){
                  return 0;
              }
            }
            else if ( j == 9 ){
              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j) != 0 &&
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j-1) != 0){
                  return 0;
              }
            }
            else{
              if ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j) != 0 &&
                    ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j-1) != 0 ||
                      RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j+1) != 0 )){
                  return 0;
              }

              //verificar se quinas encostam nos casos i=9,
              //mas 0<j<9
              if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j-1) != 0 ||
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j+1) != 0 ){
                  return 0;
              }
            }
          }

          // "num" esta na primeira coluna
          if( j == 0 ){
            
            /*os casos em que i = 0 ou i = 9 ja foram
            verificados acima*/
            if ( i > 0 && i < 9 ){
              if (( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j) != 0 ||
                    RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j) != 0 ) &&
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j+1) != 0 ){
                  return 0;
              }
            }
          }

          //  "num" esta na ultima coluna
          if( j == 9 ){
            /*os casos em que i = 0 ou i = 9 ja foram
            verificados acima*/
            if ( i > 0 && i < 9 ){
              if (( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j) != 0 ||
                    RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j) != 0 ) &&
                  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j-1) != 0 ){
                  return 0;
              }
            }
          }
        }
        else{

          /* ou seja, nao esta na borda, verificar se ha 
          navios encostados*/
          if((RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j) != 0 ||
              RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j) != 0 ) &&
            ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j-1) != 0 ||
              RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j+1) != 0 )){
              return 0;
          }

          //verificar se quinas encostam nos casos 0<i<9 e
          // 0<j<9
          if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j-1) != 0 ||
              RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i-1, j+1) != 0 ||
              RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j-1) != 0 ||
              RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i+1, j+1) != 0 ){
              return 0;
          }
        }
      }
    }
  }
  
  /*verificar se ha mais de cinco "num" em sequecia, 
  oq inidicara que ha navios encostados */
  if( maiorSequenciaX > 5){
    return 0;
  }
    


  //verificar se ha pelo menos um navio
  if ( RetornaQtdNaviosTotal( tabuleiro ) < 1 ){
    return 0;
  }

  return 1;
}


int SaoTabuleirosCompativeis( tTabuleiro tabu_1, tTabuleiro tabu_2){
  if( RetornaQtdNaviosCarrier( tabu_1 )    == RetornaQtdNaviosCarrier( tabu_2 ) &&
      RetornaQtdNaviosBattleship( tabu_1 ) == RetornaQtdNaviosBattleship( tabu_2 ) &&
      RetornaQtdNaviosCruiser( tabu_1 )    == RetornaQtdNaviosCruiser( tabu_2 ) &&
      RetornaQtdNaviosSubmarine( tabu_1 )  == RetornaQtdNaviosSubmarine( tabu_2 ) &&
      RetornaQtdNaviosDestroyer( tabu_1 )  == RetornaQtdNaviosDestroyer( tabu_2 )){
      
      return 1;
  } 
  else
    return 0;
}


tTabuleiro FechaTodasPosicoes ( tTabuleiro tabuleiro ){
  int i, j;

  for(i = 0; i < 10; i++){
    for( j = 0; j < 10; j++){
      tabuleiro.matriz[i][j][1] = 0 ; //fecha posicao
    }
  }

  return tabuleiro;
}


int HaNaviosNaoAfundados ( tTabuleiro tabuleiro ){
  int i, j;

  for(i = 0; i < 10; i++){
    for( j = 0; j < 10; j++){
      /* se houver uma posicao fechada e essa
      mesma posicao for ocupada por navio (diferente
      de 0), ainda ha navios nao afundados*/
      if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j) != 0 &&
          RetornaCondicaoPosicaoDadaDaMatriz( tabuleiro, i, j) == 0)
        return 1;
    }
  }

  return 0;
}

int EhJogadaRepetida( tJogada jogada, tTabuleiro tabuleiro){
  int linha, coluna;

  linha = RetornaLinhaJogada( jogada );
  coluna = RetornaColunaJogada( jogada );

  /*se a posicao ja foi aberta,
  ou seja, eh igual a 1,
  entao eh jogada repetida*/
  if( RetornaCondicaoPosicaoDadaDaMatriz( tabuleiro, linha-1, coluna-1) == 1 )
    return 1;
  else
    return 0;
}


tTabuleiro DeixaPosicaoVisivel ( tTabuleiro tabuleiro, tJogada jogada ){
  int linha, coluna;
  linha = RetornaLinhaJogada( jogada );
  coluna = RetornaColunaJogada( jogada );

  tabuleiro.matriz[linha-1][coluna-1][1] = 1 ; //abre posicao
  
  return tabuleiro;
}

int EhNavioAfundado ( tTabuleiro tabuleiro, int numeroNaPosicaoJogada ){
  int i, j;

  for( i = 0; i < 10; i++){
    for( j = 0; j < 10; j++){

      /*se houver alguma posicao com o id do navio
      em que esta esteja fechada, entao o navio
      nao afundou*/
      if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, i, j) == numeroNaPosicaoJogada &&
          RetornaCondicaoPosicaoDadaDaMatriz( tabuleiro, i, j) == 0 ){
          return 0;
      }
    }
  }

  return 1;
}

tTabuleiro JogaJogada ( char nomeAdversario[], tJogada jogada, 
                        tTabuleiro tabuleiro,  FILE * arquivo ){

  int  i, numeroNaPosicaoJogada, linha, coluna, qtdNaviosTotal;

  linha = RetornaLinhaJogada( jogada );
  coluna = RetornaColunaJogada( jogada );
  numeroNaPosicaoJogada =
  RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, linha-1, coluna-1);

  //abre a posicao jogada
  tabuleiro =
  DeixaPosicaoVisivel( tabuleiro , jogada );

  if( numeroNaPosicaoJogada != 0 ){
    //lembrando que o numerona posicao eh o id do navio
    if ( EhNavioAfundado( tabuleiro,  numeroNaPosicaoJogada )){

      /*um for para achar qual o navio 
      que possui o id do navio afundado */
      qtdNaviosTotal = RetornaQtdNaviosTotal( tabuleiro );
      for( i = 0; i < qtdNaviosTotal; i++){
        if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiro, i)) == 
            numeroNaPosicaoJogada)
          break;
      }

      fprintf( arquivo,"\n%s:Afundou ", 
      RetornaJogadaEmString( jogada ));
      fprintf( arquivo,"%s\n", 
      RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, i) ));
    }
    else{
      fprintf( arquivo,"\n%s:Tiro!\n", RetornaJogadaEmString( jogada ) );
    }
  }
  else{
    fprintf( arquivo,"\n%s:Agua\n", RetornaJogadaEmString( jogada ) );
  }

  return tabuleiro;
}

tTabuleiro AtualizaDadosJogadasAdversario( tTabuleiro tabuleiro, tJogada jogada){
  int qtdJogadas, l, c, q, k, idJaVerificado = 0;
  float lmedia, cmedia, lFloat, cFloat;
  

  //salva as jogadas e a qtd de tiros
  tabuleiro.dadosJogadasAdversario = 
  IncrementaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));

  qtdJogadas = RetornaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));

  tabuleiro.dadosJogadasAdversario =
  SalvaJogada ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), jogada, qtdJogadas );
  

  //linha e coluna daquela jogada
  l = RetornaLinhaJogada ( jogada );
  c = RetornaColunaJogada ( jogada );
  lFloat = l;
  cFloat = c;

  //contar tiros errados e certos 
  if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, l-1, c-1) != 0 ){
    tabuleiro.dadosJogadasAdversario = 
    IncrementaQtdTirosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));
  }
  else{
    tabuleiro.dadosJogadasAdversario = 
    IncrementaQtdTirosErrados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));
  }
    

  //salva os ids dos navios acertados se o tiro n foi na agua
  if ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, l-1, c-1) != 0){

    //q salva a qtd de navios acertados ae o momento
    q = RetornaQtdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));
    for(k = 0; k < q; k++){
      /*se um dos IDs ja salvo for igual ao ID
      da posicao, o ID desse navio ja foi verificado*/
      if( RetornaIdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), k ) == 
          RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, l-1, c-1)){
        
        idJaVerificado = 1;
        break;
      }
    }

    /*salva o id do navio acertado e a jogada
    em q isso ocooreu pela primeira vez*/
    if( !idJaVerificado ){
      tabuleiro.dadosJogadasAdversario = 
      SalvaIdDoNavioAcertadoEJogada ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), q, 
                                      RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiro, l-1, c-1) /*ID*/,
                                      qtdJogadas /*jogada em q foi acertado*/ );
      tabuleiro.dadosJogadasAdversario = 
      IncrementaQtdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));
    }
  }

  /*o desvio padrao so pode ser calculado depois
  de todas jogadas terem sido feitas*/

  return tabuleiro;
}


void ImprimeResumoDoResultadoNoArquivo ( tTabuleiro tabuleiroJogador1,   tTabuleiro tabuleiroJogador2, char nomeJogador1[], char nomeJogador2[], FILE * arquivo ){

  int i=0, qtdJogadas, l, c, idDaPosicao, k, qtdNaviosTotal;

  qtdJogadas = RetornaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ) );
  
  fprintf( arquivo, "%s\n", nomeJogador1 );

  for(i = 0; i < qtdJogadas; i++){
    fprintf( arquivo, "%s - ", 
    RetornaJogadaValidaEmString ( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i ));

    l = RetornaLinhaJogadaValida ( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i ); 
    c = RetornaColunaJogadaValida ( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i );

    /*se o tiro foi na agua (== 0) imprimir "Agua", se nao
    imprimir "Tiro - nomeNavio - IDNavio"*/
    /*lembrando que [x][y][0] guarda o id do navio 
    naquela posicao, se n tiver navio eh zero*/
    if( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiroJogador2, l-1, c-1) == 0){
      fprintf( arquivo, "Agua\n");
    }
    else{
      /*temos que identificar o id do navio que esta na 
      posicao e o nome do navio*/
      idDaPosicao = RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiroJogador2, l-1, c-1);

      /*um for para achar qual o navio 
      que possui o id do navio atingido */
      qtdNaviosTotal = RetornaQtdNaviosTotal( tabuleiroJogador2 );
      for( k = 0; k < qtdNaviosTotal; k++){
        if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiroJogador2, k)) == idDaPosicao)
          break;
      }

      fprintf( arquivo, "Tiro - %s - ID %02d\n",
      RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiroJogador2, k) ), idDaPosicao);
    }
  }

  //MESMA COISA PRO JOGADOR 2
  fprintf( arquivo, "\n");
  qtdJogadas = RetornaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ));
  
  fprintf( arquivo, "%s\n", nomeJogador2 );


  /*lembrando que as jogadas do jogador 1
  estao salvas no tabuleiro 2, e do jogador 2
  esta no tabuleiro 1*/

  for(i = 0; i < qtdJogadas; i++){
    fprintf( arquivo, "%s - ",
    RetornaJogadaValidaEmString ( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i ));

    l = RetornaLinhaJogadaValida ( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i ); 
    c = RetornaColunaJogadaValida ( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i );

    /*se o tiro foi na agua (== 0) imprimir "Agua", se nao
    imprimir "Tiro - nomeNavio - IDNavio"*/
    /*lembrando que [x][y][0] guarda o id do navio 
    naquela posicao, se n tiver navio eh zero*/
    if ( RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiroJogador1, l-1, c-1) == 0 ){
      fprintf( arquivo, "Agua\n" );
    }
    else{
      /*temos que identificar o id do navio que esta na 
      posicao e o nome do navio*/
      idDaPosicao = RetornaNumeroNaPosicaoDadaDaMatriz( tabuleiroJogador1, l-1, c-1);

      /*um for para achar qual o navio 
      que possui o id do navio atingido */
      qtdNaviosTotal = RetornaQtdNaviosTotal( tabuleiroJogador1 );
      for( k = 0; k < qtdNaviosTotal; k++){

        if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiroJogador1, k) ) == idDaPosicao)
          break;
      }

      fprintf( arquivo, "Tiro - %s - ID %02d\n", 
      RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiroJogador1, k) ), idDaPosicao);
    }
  }

  /*o resultado (vencedor ou empate) sera imprido
  na main, ja que posso a mesma estrurara ja montada
  la pra imprimir esse mesmo resultado no arquivo de
  saida*/
}


tTabuleiro OrdenaNaviosAcertadosEmOrdemCrescente( tTabuleiro tabuleiro ){

  int i, j, k, l, qtdNaviosAcertados, id1, id2, jogada1, jogada2, qtdNaviosTotal;
  
  qtdNaviosAcertados =
  RetornaQtdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ));

  for( i = 0; i < qtdNaviosAcertados; i++){
    for(j = i+1; j < qtdNaviosAcertados; j++){
      
      id1 = RetornaIdNaviosAcertados ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), i) ;
      id2 = RetornaIdNaviosAcertados ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), j );
      jogada1 = 
      RetornaJogadaNavioFoiAcertadoPrimeiraVez ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), i );
      jogada2 = 
      RetornaJogadaNavioFoiAcertadoPrimeiraVez ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), j );

      /*um for para achar qual o navio possui id1*/
      qtdNaviosTotal = RetornaQtdNaviosTotal( tabuleiro );
      for( k = 0; k < qtdNaviosTotal; k++){
        if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiro, k)) == id1)
          break;
      }
      /*um for para achar qual o navio possui id2*/
      for( l = 0; l < qtdNaviosTotal; l++){
        if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiro, l) ) == id2)
          break;
      }

      //ordem alfabetica
      if( strcmp( tabuleiro.naviosDoTabuleiro[k].nomeNavio,
                  tabuleiro.naviosDoTabuleiro[l].nomeNavio) > 0){

        tabuleiro.dadosJogadasAdversario = 
        SalvaIdDoNavioAcertadoEJogada( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), i, id2, jogada2);
        tabuleiro.dadosJogadasAdversario = 
        SalvaIdDoNavioAcertadoEJogada( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), j, id1, jogada1);
      }
      //se for nome igual, o navio q levou o tiro primeiro vem antes
      else if( strcmp ( RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, k) ),
                        RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiro, l) )) == 0 ){

        if( RetornaJogadaNavioFoiAcertadoPrimeiraVez ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), i) >
            RetornaJogadaNavioFoiAcertadoPrimeiraVez ( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), j )){
          
			tabuleiro.dadosJogadasAdversario = 
			SalvaIdDoNavioAcertadoEJogada( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), i, id2, jogada2);
			tabuleiro.dadosJogadasAdversario = 
			SalvaIdDoNavioAcertadoEJogada( RetornaDadosDasJogadasNoTabuleiro( tabuleiro ), j, id1, jogada1);
        }
      }
    }
  }

  return tabuleiro;
}



void ImprimeEstatisticasNoArquivo( tTabuleiro tabuleiroJogador1,   tTabuleiro tabuleiroJogador2, char nomeJogador1[], char nomeJogador2[], FILE * arquivo ){

  int i, k, l, c, qtdJogadas, tirosErrados = 0, tirosCertos = 0, 
  qtdNaviosTotal, qtdNaviosAcertados, id, jogada;
  float lcentroide, ccentroide;
  float lFloat, cFloat, lmediaFloat, cmediaFloat, desvioPadrao, somatorioDesvioPadrao;

  fprintf( arquivo, "%s\n", nomeJogador1 );
  //DADOS JOGADOR 1
  /*lembrando que esses dados estao no tabuleiro adversario,
  pois esse jogador jogou baseado no tabuleiro do adversario*/
  qtdJogadas = RetornaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ));
  tirosErrados = RetornaQtdTirosErrados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ));
  tirosCertos = RetornaQtdTirosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ));

  fprintf( arquivo, "Tiros Errados: %d\n",  tirosErrados);
  fprintf( arquivo, "Tiros Acertados: %d\n",  tirosCertos);

  /* soma das localizacoes Media para calc da media*/
  for(i = 0; i < qtdJogadas; i++){
    lFloat = RetornaLinhaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i);
    cFloat = RetornaColunaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i);
    tabuleiroJogador2.dadosJogadasAdversario = 
    AtualizaSomaDasLocalizacoes( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), lFloat, cFloat );
  }

  lcentroide =
  RetornaSomaLocalizacoesLinha( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 )) / qtdJogadas;
  ccentroide =
  RetornaSomaLocalizacoesColuna( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 )) / qtdJogadas;
  fprintf( arquivo, "Localizacao Media: (%0.2f,%0.2f)\n",
  lcentroide, ccentroide);
  
  //somatorio desvio padrao
  for(i = 0; i < qtdJogadas; i++){
    lFloat = RetornaLinhaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i);
    cFloat = RetornaColunaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i);
    tabuleiroJogador2.dadosJogadasAdversario =
    AtualizaSomatorioDesvioPadrao( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), 
              (pow(( lFloat - lcentroide ), 2) + pow(( cFloat - ccentroide ), 2)));
  }

  somatorioDesvioPadrao = 
  RetornaSomatorioDesvioPadrao( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ));

  desvioPadrao = sqrt(( somatorioDesvioPadrao / qtdJogadas ));
  fprintf( arquivo, "Desvio Padrao da Localizacao: %0.2f\n",  desvioPadrao );
  
  //imprimir navios acertados do jogador 1
  /*importante lembrar que os dados das jogadas
  do jogador estao no tabuleiro adversario, 
  porem aqui eh solicitado infomar os navios
  atingidos de seu proprio tabuleiro*/
  fprintf( arquivo, "Navios de %s:\n", nomeJogador1 );

  tabuleiroJogador1 = 
  OrdenaNaviosAcertadosEmOrdemCrescente( tabuleiroJogador1 );
  qtdNaviosAcertados = 
  RetornaQtdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ));

  for( i = 0; i < qtdNaviosAcertados; i++ ){
    id = RetornaIdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i);
    //jogada se refere a jogada em q o navio foi atingido pela primeira vez
    jogada = 
    RetornaJogadaNavioFoiAcertadoPrimeiraVez( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i);

    /*um for para achar qual o navio 
    que possui esse id*/
    qtdNaviosTotal = RetornaQtdNaviosTotal( tabuleiroJogador1 );
    for( k = 0; k < qtdNaviosTotal; k++){
      if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiroJogador1, k)) == id)
        break;
    }

    fprintf( arquivo, "%02d - %s - ID %02d\n", 
    jogada, RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiroJogador1, k)), id);
  }

  fprintf( arquivo, "\n");
  //MESMA COISA PRO JOGADOR 2

  fprintf( arquivo, "%s\n", nomeJogador2 );
  //DADOS JOGADOR 2
  //lembrando que esses dados estao no tabuleiro adversario
  qtdJogadas = RetornaQtdJogadas( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ));
  tirosErrados = RetornaQtdTirosErrados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ));
  tirosCertos = RetornaQtdTirosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ));

  fprintf( arquivo, "Tiros Errados: %d\n",  tirosErrados);
  fprintf( arquivo, "Tiros Acertados: %d\n",  tirosCertos);

  /* soma das localizacoes Media para calc da media
  e soma dos tiros acertados/errados*/
  /*reiniciar os valores se nao continuaria contando os
  tiros do jogador 1*/
  tirosCertos = 0;
  tirosErrados = 0;

  for(i = 0; i < qtdJogadas; i++){
    lFloat = RetornaLinhaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i);
    cFloat = RetornaColunaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i);
    tabuleiroJogador1.dadosJogadasAdversario = 
    AtualizaSomaDasLocalizacoes( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), lFloat, cFloat );
  }

  lcentroide =
  RetornaSomaLocalizacoesLinha( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 )) / qtdJogadas;
  ccentroide =
  RetornaSomaLocalizacoesColuna( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 )) / qtdJogadas;

  fprintf( arquivo, "Localizacao Media: (%0.2f,%0.2f)\n",
  lcentroide, ccentroide);
  
  //somatorio desvio padrao
  for(i = 0; i < qtdJogadas; i++){
    lFloat = RetornaLinhaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i);
    cFloat = RetornaColunaJogadaValida( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), i);
    tabuleiroJogador1.dadosJogadasAdversario =
    AtualizaSomatorioDesvioPadrao( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ), 
              (pow(( lFloat - lcentroide ), 2) + pow(( cFloat - ccentroide ), 2)));
  }

  somatorioDesvioPadrao = 
  RetornaSomatorioDesvioPadrao( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador1 ));

  desvioPadrao = sqrt(( somatorioDesvioPadrao / qtdJogadas ));
  fprintf( arquivo, "Desvio Padrao da Localizacao: %0.2f\n",  desvioPadrao );
  
  //imprimir navios acertados do jogador 1
  /*importante lembrar que os dados das jogadas
  do jogador estao no tabuleiro adversario, 
  porem aqui eh solicitado infomar os navios
  atingidos de seu proprio tabuleiro*/
  fprintf( arquivo, "Navios de %s:\n", nomeJogador2 );

  tabuleiroJogador2 = OrdenaNaviosAcertadosEmOrdemCrescente( tabuleiroJogador2 );
  qtdNaviosAcertados = 
  RetornaQtdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ));

  for( i = 0; i < qtdNaviosAcertados; i++ ){
    id = RetornaIdNaviosAcertados( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i);
    //jogada se refere a primeira jogada em q o navio foi atingido
    jogada = 
    RetornaJogadaNavioFoiAcertadoPrimeiraVez( RetornaDadosDasJogadasNoTabuleiro( tabuleiroJogador2 ), i);

    /*um for para achar qual o navio 
    que possui esse id*/
    qtdNaviosTotal = RetornaQtdNaviosTotal( tabuleiroJogador2 );
    for( k = 0; k < qtdNaviosTotal; k++){
      if( RetornaIDNavio( RetornaNavioDoTabuleiro( tabuleiroJogador2, k) ) == id)
        break;
    }

    fprintf( arquivo, "%02d - %s - ID %02d\n", 
    jogada, RetornaNomeNavio( RetornaNavioDoTabuleiro( tabuleiroJogador2, k) ), id);

  }
}

void ImprimeNaviosNoArquivo( tTabuleiro tabuleiro, FILE* arquivo){

  int qtdNavios, i;
  tNavio navio;
  qtdNavios = RetornaQtdNaviosTotal( tabuleiro );

  for( i = 0; i < qtdNavios; i++ ){
    navio = RetornaNavioDoTabuleiro( tabuleiro, i);
    fprintf( arquivo, "%s;", RetornaNomeNavio( navio ));
    fprintf( arquivo, "%d;", RetornaIDNavio( navio ));
    fprintf( arquivo, "%d;", RetornaOrientacaoNavio( navio ));
    fprintf( arquivo, "%c", RetornaCoordenadaLinhaInicioNavio( navio ));
    fprintf( arquivo, "%d", RetornaCoordenadaColunaInicioNavio( navio ));
    if( i < qtdNavios-1 )
      fprintf( arquivo, "\n");
  }
}

//GERAR TABULEIRO VALIDO
void GeraTabuleiroValido ( FILE * arquivo, char* diretorio ){
    int i,j;
   FILE * Arquivo_ImprimirTabuleiro;

    tTabuleiro tabuleiro;

    srand( time( NULL ));
    
    for(i = 0;i < 5; i++){
      /*uso o arquivo de destino como um hospedeiro 
      temporario para guardar um navio e depois verifico 
      se ele eh valido juntos aos outros navios ja 
      guardados, se sim, salvo ele como um navio do 
      tabuleiro*/
      //criar um navio de cada tipo em ordem alfabetica
      if( i == 0 ){
        fprintf( arquivo, "Battleship;" );
      }
      else if( i == 1 ){
        fprintf( arquivo, "Carrier;");
      }
      else if( i == 2 ){
        fprintf( arquivo, "Cruiser;");
      }
      else if( i == 3 ){
        fprintf( arquivo, "Destroyer;");
      }
      else if( i == 4 ){
        fprintf( arquivo, "Submarine;");
      }

      //coloca o id do navio
      fprintf( arquivo, "%d;", i+1);
      //cria uma orientacao (aleatoria)
      fprintf( arquivo, "%d;", rand() % 2 );
      //cria uma posicao aleatoria para o navio
      fprintf( arquivo, "%c", 'a' + rand() % 10 );
      fprintf( arquivo, "%d", 1 + rand() % 10 );
      fprintf( arquivo, "\n");

      //fecha o arquivo para abrir ele para leitura
      fclose( arquivo );
      arquivo = fopen( diretorio, "r");

      //ler o navio salvo temporariamente no arquivo de saida
      tabuleiro.qtdNaviosTotal = i+1;
      tabuleiro.naviosDoTabuleiro[i] = LeNavio( arquivo );

      //salvar tamanho do navio
      if( i == 0 ){
        //"Battleship", tamanho = 4
        tabuleiro.naviosDoTabuleiro[i] = 
        SalvaTamanhoNavio( tabuleiro.naviosDoTabuleiro[i], 4);
      }
      else if( i == 1 ){
        //"Carrier", tamanho = 5
        tabuleiro.naviosDoTabuleiro[i] = 
        SalvaTamanhoNavio( tabuleiro.naviosDoTabuleiro[i], 5);
      }
      else if( i == 2 ){
        //"Cruiser", tamanho = 3
        tabuleiro.naviosDoTabuleiro[i] = 
        SalvaTamanhoNavio( tabuleiro.naviosDoTabuleiro[i], 3);
      }
      else if( i == 3 ){
        //"Destroyer", tamanho = 2
        tabuleiro.naviosDoTabuleiro[i] = 
        SalvaTamanhoNavio( tabuleiro.naviosDoTabuleiro[i], 2);
      }
      else if( i == 4 ){
        //"Submarine", tamanho = 3
        tabuleiro.naviosDoTabuleiro[i] = 
        SalvaTamanhoNavio( tabuleiro.naviosDoTabuleiro[i], 3);
      }
      
      /* se ao adicionar o navio no tabuleiro ele nao for
      valido, gerar um novo navio daquele tipo, com novos 
      dados, ateh que o tabuleiro passe a ser valido*/
      if( !EhTabuleiroValido( tabuleiro ))
        i--;


      /*apos ler o navio, abrir novamente o arquivo para
      escrita para escrever o novo navio nele*/
      fclose( arquivo );
      arquivo = fopen( diretorio, "w");
    }
    
    ImprimeNaviosNoArquivo( tabuleiro, arquivo );

    /*se quiser visualizar o tabuleiro aberto, eh so 
    descomentar a parte abaixo, porem o endereco do
    arquivo de destino deve ser colocado a mao*/
    /*
    Arquivo_ImprimirTabuleiro = fopen( "meuTeste/tabuleiro.txt", "w");
    
    tabuleiro = IniciaMatrizDoTabuleiro( tabuleiro );
    
    for( i = 0; i < 10; i++){
      for( j = 0; j < 10; j++){
        tabuleiro.matriz[i][j][1] = 1;
      }
    }

    ImprimeTabuleiroNoArquivo( tabuleiro , Arquivo_ImprimirTabuleiro );
    
    fclose(Arquivo_ImprimirTabuleiro);
    */
}
