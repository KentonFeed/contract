1. Запускаем консоль нажатием ПКМ на папке блокчейна, затем на фразу "Git bash here".
2. Вводим приведенную ниже команду для генерации параметров блокчейна из генезис файла:

geth --identity  "yourldentity" --datadir "./" init ./genesis.json

3. Вводим приведенную ниже команду для запуска ноды (первая команда для новой версии, вторая - для старой):

geth --networkid 67878 --http --http.port="8545" --http.corsdomain="http://remix.ethereum.org" --http.api="web3,eth,debug,personal,net" --vmdebug --datadir "./" --dev --allow-insecure-unlock

geth --datadir "./" --networkid 67878 --rpc  --rpcport "8545"  --rpcapi="web3,eth,debug,personal,net"  --rpccorsdomain "*" --allow-insecure-unlock 

4. Запускаем вторую консоль нажатием ПКМ на папке блокчейна, затем на фразу "Git bash here".  
5. Вводим во вторую консоль команду ниже для развертывания пользовательского интерфейса блокчейна:

geth attach "//./pipe/geth.ipc"

Команда для создания нового кошелька: personal.newAccount()
Команда для смены основного кошелька (кошелька майнинга): miner.setEtherbase(eth.accounts[1])
Команда запуска майнинга: miner.start()
Команда остановки майнинга: miner.stop()
Команда для разблокировки кошелька: personal.unlockAccount(eth.accounts[0], "ваш пароль")
Команда вывода кошельков: eth.accounts
Команда вывода баланса кошелька: eth.getBalance(eth.accounts[0])
Команда для проверки номера блока: eth.blockNumber


