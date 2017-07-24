all: clean root-cert server-creds move

server-creds:
	~/certstrap/bin/certstrap request-cert --cn "snaptest-srv" --ip "127.0.0.1" --domain "localhost" --passphrase '' --key-bits 2048 --o "snaptest" --ou "server"
	~/certstrap/bin/certstrap sign "snaptest-srv" --CA "snaptest-ca" --passphrase '<ca-secure-passphrase>' --years 1

root-cert:
	~/certstrap/bin/certstrap init --cn "snaptest-ca" --o "snaptest" --ou "ca" --key-bits 2048 --years 1 --passphrase '<ca-secure-passphrase>'

move:
	mv ~/certstrap/out/* ./out/
clean:
	rm -f out/*
