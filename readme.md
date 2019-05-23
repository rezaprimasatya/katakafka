<h1>how to ne</h1>

docker network create kafka-network
#buat komunikasi yang lebih baik antara app sama kafka cluster

docker-compose -f docker-compose.kafka.yml up -d
#jalanin di background single-node Kafka cluster

docker-compose -f docker-compose.kafka.yml logs -f broker | grep "started"
#bunch ngecek status


<h1>make' nya</h1>

docker-compose -f docker-compose.kafka.yml exec broker kafka-console-consumer --bootstrap-server localhost:9092 --topic T
#queuing.transactions: raw generated transactions
#streaming.transactions.legit: legit transactions
#streaming.transactions.fraud: suspicious transactions



<h1>Tear Down</h1>
docker-compose down

docker-compose -f docker-compose.kafka.yml stop
#sekalian matiin kafka cluster nya

docker network rm kafka-network
#buat hapur kenangan