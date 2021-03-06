# bad-robot.framework

Imagine um programa de computador que, observando a movimentação dos preços de um ativo ao longo do tempo, é capaz de, sozinho, sem interferência humana, determinar a hora de comprá-lo ou vendê-lo.

## Getting Started

Esse projeto foi desenvolvido para facilitar a criação de robôs traders escritos na linguagem [mql5](https://www.mql5.com/pt)
para a plataforma metatrader 5. Todos os robôs encontram em seus respectivos repositórios, acompanhados de um arquivo .set 
de configuração da estratégia.

* [first-candle](https://github.com/erlonfs/first-candle.bad-robot)
* [box](https://github.com/erlonfs/box.bad-robot)
* [line](https://github.com/erlonfs/line.bad-robot)
* [elephant-walk](https://github.com/erlonfs/elephant-walk.bad-robot)

Para comecar um novo projeto, pode se utilizar o exemplo base:

[mt5-sample-robot](https://github.com/erlonfs/sample.bad-robot)

```c
#include <Trade\Trade.mqh>
#include <Trade\PositionInfo.mqh>
#include <BadRobot.Framework\BadRobot.mqh>

class Sample : public BadRobot
{
	private:
   
	MqlRates _rates[];
   
	public:
	  
	void Load() 
	{
		//Logic Here
	};

	void Execute() {

		if(!BadRobot::ExecuteBase()) return;
			
		//Logic Here
		   
	};

	void ExecuteOnTrade(){

		BadRobot::ExecuteOnTradeBase();
	 
		//Logic Here
	 
	};
};
```

Inicialmente o projeto foi feito para atender ao mercado de BMF, mais especificamente os mini-contratos 
de índice e dólar. Para compilar os robôs é necessario acessar o editor de código do metatrader 5.

Cada robô possui sua estratégia, contudo todos possuem funcionalidades basicas em comum, muitas delas já conhecidas 
no mercado de negociação.

| Função | Possui |
| ------ | ------ |
|Stop Gain | SIM |
|Stop Loss | SIM|
|Stop no candle anterior | SIM|
|Horário de inicio e fim | SIM|
|Horário de intervalo | SIM |
|Trailing Stop | SIM|
|Break-even | SIM|
|Saída Parcial | SIM|
|Gerenciamento Financeiro | SIM|
|Notificações no App MT5 | SIM|