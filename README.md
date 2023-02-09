# appathonpro2023

import socket as s

# server info
hostIP, port = s.gethostname(), 5050

#### CONFIGURATION ####
serverSocket = s.socket()    # socket inst for server
serverSocket.bind((hostIP, port))
serverSocket.listen()

#### serving client ####

def acceptClient():
    print("connecting...")
    clientSocket, clientInfo = serverSocket.accept()      # client tings
    print("connected to {cient}".format(clientSocket.gethostbyname()))
    clientSocket.send("hello")


if __name__ == "__main__":
    while True:
        acceptClient()

