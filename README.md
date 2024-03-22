# Messaging system based on the Kerberos protocol


How to run the project:
    running the authentication server from the 'server' dictionary:    python auth_server_main.py
    running the message server from the 'server' dictionary:           python msg_server_main.py
    running the client from the 'client_handler' dictionary:           python main_client.py

The attack code explained:
    I "pulled" values ​​from the communication and use them as constants in the 'users.txt' file in the 'dic_attack' dictionary.
    The values that I "pulled" are client_id, nonce and (nonce + aes_key) encrypted.
    Every 3 lines consecutively in the 'users.txt' file are information about a specific client.
    The first line is client_id. The second line is nonce. The third line is (nonce + aes_key) encrypted.
    
    The script 'attack.py' is using the 'password.txt' file to try to decrypt the (nonce + aes_key) and if there is a match between the 
    given nonce from the 'user.txt' file and the decrypted nonce then the password was discoverd for UUID.
    The script 'attack.py' will do a dictionary attack and try to discover passwords for UUID.
