Anton Documentation
===============

## Time Frame
This took me about 3 and half weeks to make, and their is alot more things I didn't mention inside of this documentation

## Anton Description

Anton is an AI that can run without requiring Wi-Fi and utilizes one of the fastest algorithms available. Its code is optimized to operate on any Mac computer, as it utilizes specific libraries exclusive to Mac OS systems.

## Code Description

Anton has a huge amount of features used, and this will be a long page. So I will only show important things in Antons Source Code.

###### Algorthim Used
Anton utilizes the [Quicksort algorithm](https://en.wikipedia.org/wiki/Quicksort) for sorting data and storing it. The algorithm efficiently sorts through the data provided to it or data accumulated on its own. With C++ being a naturally fast language, the algorithm’s performance is further enhanced.

###### Debuge Proccess

As a helpful assistant, I want to let you know that a Debugger is a useful tool for identifying and fixing bugs or errors in programming code. However, I have taken the process up a notch by enabling Anton to autocorrect itself using an automatic debugger, without requiring constant monitoring from me. To achieve this, I created functions that can pinpoint errors and provide solutions for fixing them.

```cppp
int WrongPasswordFunction(){

  std::string password = "AntonMadeThisPasswordItContainsMoreCharactersThenANormalPassword912345";
  std::string ErrorPassword;
  // std::cout << "Wrong Password This will be reported to Antons Internal Database \n";
  std::cout << "You have 1 more try to get access the to dev tools: ";
  std::cin >> ErrorPassword;

  if(ErrorPassword == password){
    return true; // returns true if the password is correct 
  }else{
    
    system("clear");
    std::cout << "Wrong password this will be reported to Antons database \n";

    std::ofstream ErrorFile("Wrong Password Input.txt");
    ErrorFile << "Anton has reported a user had inputed a wrong password for the Dev tools login, This might be a secruity issue and should be checked into. \n";
    ErrorFile << "The user inputed " << ErrorPassword << "\n";
    ErrorFile.close();
    return false;
  } 
  return 0;
}
```

As seen in the code, there is a function named WrongPasswordFunction() that is triggered whenever the User enters an incorrect password. This code is executed by Anton to handle the issue and the problem is then saved in a file for future reference.

###### Database

In order for any AI to function properly, it requires a database to store information such as user passwords, usernames, and messages. These databases are connected to the backend server. In my case, I created four different databases.

```cpp
#pragma once

#include <iostream>
#include <string>
#include <fstream>
#include <unistd.h>

int DataBase(){

  std::string option;
  std::string dataInput;
  std::string dataInput2;
  std::string dataInput3;
  std::string path = "Data.txt";
  
  int indexInserter;
  
    // we make a file function then we close it!
  std::ofstream File;
  File.open("Data.txt");
  File.close();
  
  std::string dataEntries[4] = {"DeleteThis",};

  std::cout << "Which index do you want your data to be inputed in, 1,2,3 \n";
  std::cin >> indexInserter;

  switch(indexInserter){
    case 1:
      std::cout << "Index 1 Data:";
      std::cin.ignore();
      std::getline(std::cin, dataInput);
      dataEntries[1] = dataInput;

      // break;
    case 2:
      std::cout << "Index 2 Data:";
      std::cin.ignore();
      std::getline(std::cin, dataInput2);
      dataEntries[2] = dataInput2;
      // break;
    case 3: 
      std::cout << "Index 3 Data:";
      std::cin.ignore();
      std::getline(std::cin, dataInput3);
      dataEntries[3] = dataInput3;
      break;
  }

  if(dataEntries[1].empty()){
    std::cout << "Index 1 is empty \n";
    sleep(2);
  }else{
    std::cout << "Index 1 is not empty, index 1 contains " << dataInput << '\n';
    sleep(2);
  }

  if(dataEntries[2].empty()){
    std::cout << "Index 2 is empty \n";
    sleep(2);
  }else{
    std::cout << "Index 2 is not empty, index 2 contains " << dataInput2 << '\n';
    sleep(2);
  }

  if(dataEntries[3].empty()){
    std::cout << "Index 3 is empty \n";
    sleep(2);
  }else{
    std::cout << "Index 3 is not empty, index 3 contains " << dataInput3 << '\n';
    sleep(2);
  }

  File.open("Data.txt");
  File << "{\n";
  File << "   " << dataInput << '\n';
  File << "   " << dataInput2 << '\n';
  File << "   " << dataInput3 << '\n';
  File << "}\n";
  File.close();

  return 0;
}
```

This is the most current version of the database available. The code consists of an array that stores all data. Users can input data into specific indexes of the array. The code checks if the indexes are full. If they are, it informs the user that the array is full and displays the data in those specific arrays, so the user can see what's inside.

There are two databases: the `Internal Database` and the `External Database`. The Internal Database contains all the data Anton collects, including private data, which is securely stored. The External Database is used for public data, such as the last time Anton was run, the last code edit, and the date and time of logins.

###### User Shell

Whenever you run Anton, it has something called `The Shell`, The Shell seperates normal users from Developers, The developers have access to the source code and the very special thing called the `Dev Tools`

Dev Tools Contain:

> - Compile from source
> - Edit the all the code
> - Complete access to the Internal Database

Whenever Anton is ran, it will show the current Shell the user is in with their username.

###### Virus

I have a program that I refer to as the `Virus`. It’s designed to completely erase Anton from existence, but it’s only accessible with two passwords that are each 147 characters long and comprised of 23-29 words. 

I call it the Virus because once it's activate it, the code corrupts itself, making it unreadable to anyone who tries to access it after the fact.

``` 
\s���(?Vm����
$;Ri������   #[r������*AX����
!8Of}����`w����-D[r������*AXo������2I`w���
�8Of}�c�+�5���`RC!s��g�.:Ny-�gR.��wg��xs|��dx,���x�X̍k�-j�/�m���3nNZ+��s-u���
 �vZT��s�a�r�2Nw3+[~	%7�����$q$�j
�ִ�f��p:
       ?
����3
     4
z@�
�n��IP�t��L��
             �
1O����[{*�� #���#
                 ��J$�a��y��mo�	Z��X/k]���j�
�$ʷ;j$)怓l����;�J�!�)M�\�Ws��5"�:uSV��!��"��nh%��T{v35��3��C���3���sܾb�˹�q��Qc�3t��	�x�msY�8"��j$����s$1u����s�$��@
�Hk$q��5d$,su4� f�-�WV6,� sd���si,���}|�;�sڶ�!Ih���k"j�bs�7"
                                                   q
�r[��%������fF^@�b��m$�,�/u�Y{3wH��X�O�2��ik�4�tO�[Lm�>t;���|�2`I ��F��8-��L{q�-�

	N:�U��m$w/8h�.��Q3�5k$σH�ַsj)פ�F�t�y�Z'L@"Y�'�p<��?IF Z�>��0*D�id8|��O�/="6]vm�z��8��9n��m/f���
                                                                                                      �
�^D��i�?�����=���B�?�r��_�*���e��I�f���Xh��r��is�s��eI-���UY�(t�޷Z��Ndբ�FS�����A��������N�
ZQ �����0S<���8��y�&Q�'�b~]�e!�3�wm$�W�DR�#�}�n

7%��$�5�,*	|l,�$?�-�pm$I�+Sv$U*H��lR��i��~j$������;>��:��v���F�
s���xLf�-���#��l$�W$�[��m��}��<�G4�W�F�fc/�
06`�
8�
f�g;��ƻ�NJ��ʅ[��+�`�!��
 �N��$�sa�x�P-#`}x��f	.t�����q|�@d/,�h>���<&�3���7��l\��x�ea-�L�9�b�#�ͻ�s
                                                                           �F
Qe���i�/Z�#���Ł/��_T�Xf��Q�Z���"��$���vN5�B�h�.X�>��snȸFB�~m$v���T�=�J��S޹�q�E1I\ )��N���TRT���,��i}?�9H����Z1�]���9eK��qPwI�a_[/����j$W�{��������|�

���_� u1�W�!���_�3�f�hPj�/|}���
n{��vڻ�s��F4�+s����G$�j{���j$�(:
                                M��ibB$(
                                        �a?�-<
�]u���t��F�As��-f�-��g	N�}��vC5N��31R�#8�9PUR�#e�DS�$�ǖ�����)�k�
|�1\%�                                                           �	X�][��m$��d��0j{GnI�|�wFH�^=��8}�8�_S&�]hb���-�.Ć���s Z�S	��	�`=�6sQ��x_
HSAH� ���c�+HKö���o3�!IETӹ#)�^�j$�K��&�Z�m�����	��rDp�J�!s�����s��O�Lsg�?�
    ����%
```

Once executed, there is no going back as there is no decrypter to decipher this code.

