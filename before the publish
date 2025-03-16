import base64

def base(list_of_words):
    binary_string = ''.join(list_of_words)
    padding_length = (8 - len(binary_string) % 8) % 8
    binary_string += '0' * padding_length 
    data_bytes = int(binary_string, 2).to_bytes(len(binary_string) // 8, byteorder='big')
    base64_encoded = base64.b64encode(data_bytes)
    
    return base64_encoded.decode('utf-8')

def str_to_bin(plain_text):
    return ''.join(format(ord(char), '08b') for char in plain_text)

def split_4(text):
    return [text[i:i + 4] for i in range(0, len(text), 4)]

def is_even(number):
    return number % 2 == 0

def add_0_1(list_of_words):
    for i in range(len(list_of_words)):
        chunk = list_of_words[i] 
        if is_num_of_1_even(chunk):
            list_of_words[i] += '0'  
        else:
            list_of_words[i] += '0' 
    return list_of_words

def is_num_of_1_even(word):
    num = word.count('1')
    return is_even(num)

def encryption(the_flag):
    cipher_1 = str_to_bin(the_flag)
    
    cipher_2 = split_4(cipher_1)
    
    cipher_3 = add_0_1(cipher_2)
    
    final_cipher = base(cipher_3)
    
    return final_cipher

final_cipher = encryption(flag)
print("Final cipher:", final_cipher)

