    if (parar == true || velocidade <= 0) {
        carromovimenta = "está parado";
        System.out.println("carro esta parado para ele precisa de uma arrancada para andar");
    } else {
        carromovimenta= " carro em movimento";
    };

    String carroPT= """
            O carro ultrapassou o seu limite e com isso acabou dando PT
            Tome mais cuidado na proxima vez!
            """;



    String menu = """
            |________________________________________|
                          
                              Menu            
                                
            1: acelerar       
            2: reduzir        
            3: buzinar        
            4: parar          
            5: arrancar  
                 
            ///////////////////////
            
            carro: %s           
            velocidade: %d km/h 
            aceleração: %d
            |________________________________________|
            Escolha um numero para conduzir o veiculo
            """.formatted(carromovimenta,velocidade,aceleracao);
    System.out.println(menu);
    escolha = scanner.nextInt();
    while(escolha !=5){


        if (parar == true || velocidade <= 0) {
            carromovimenta = "está parado";
            System.out.println("carro esta parado para ele precisa de uma arrancada para andar");
        } else {
            carromovimenta= " carro em movimento";
        };


        if(velocidade >= 181){
            System.out.println(carroPT);
            System.exit(0);
        }

        switch (escolha){
            case 1:
                System.out.println("Voce acelerou 1, logo sua velocidade aumentou");
                aceleracao ++;
                velocidade = velocidade + aumentarvelocidade;
                if(velocidade >=181){
                    System.out.println(carroPT);
                    System.exit(0);
                }
                Thread.sleep(1000);
                break;

            case 2:
                if(aceleracao<=0){
                    System.out.println("voce está perdendo velocidade");
                    velocidade  = 0;
                }else{
                    System.out.println("Voce desacelerou 1");
                    aceleracao--;
                    velocidade = reduzirvelocidade;
                };
                Thread.sleep(1000);
                break;

            case 3:

                String Buzinar = """
                       
                        FOM
                       
                        FON
                       
                        FOn
                       
                        Fon
                       
                        fon""";
                System.out.println(Buzinar);
                Thread.sleep(1500);
                break;

            case 4:
                System.out.println("voce esta fazendo uma parada brusca");
                aceleracao = 0;
                velocidade = 0;
                parar = true;
                Thread.sleep(1000);
                break;
            case 5:
                if(parar == true){
                    aceleracao++;
                    velocidade = aumentarvelocidade;
                }else {
                    velocidade = aumentarvelocidade;
                };
                Thread.sleep(1000);
                break;

            default:
                System.out.println("o carro nao correspondeu como voce queria e explodiu!");
                Thread.sleep(1000);
                System.exit(0);

                break;

        }
        System.out.println(menu);
        System.out.println("gostaria de buzinar mais uma vez, se sim aperte 3 se nao aperte outra tecla ");
        escolha = scanner.nextInt();


    }

}
