# SVV_NODE

git clone https://github.com/goooodnes/SVV_NODE.git

cd SSV_NODE

## Password file

echo "<MY_OPERATOR_PASSWORD>" >> password

## Key pair generation and encryption

docker run --name ssv-node-key-generation -v "$(pwd)/password":/password -it "bloxstaking/ssv-node:latest" /go/bin/ssvnode generate-operator-keys --password-file=password && docker cp ssv-node-key-generation:/encrypted_private_key.json ./encrypted_private_key.json && docker rm ssv-node-key-generation


## Start network

docker-compose up -d
