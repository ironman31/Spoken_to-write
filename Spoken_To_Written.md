```python
import numpy as np

       
              
```


```python
def get_rules():
    rules = {"Numbers":{
                        "zero": '0',
                        "one" : '1',
                        "two": '2',
                        "three": '3',
                        "four": '4',
                        "five": '5',
                        "six": '6',
                        "seven": '7',
                        "eight": '8',
                        "nine": '9',
                        "ten": '10',
                        "twenty": '20',
                        "thirty": '30',
                        "forty": '40',
                        },
            "Tuples": {
                         "Single":1,
                         "Double":2,
                         "Triple":3,
                         "Quadruple":4,
                         "Quintuple":5,
                         "Sextuple":6,
                         "Septuple":7,
                         "Octuple":8,
                         "Nonuple":9,
                         "Decuple":10
                      },
            "General": {
                          "C M": "CM",
                          "P M": "PM",
                          "D M": "DM",
                          "A M": "AM"
                       },
            "Currancy":{
                            "dollars":"$"
                            
                 
                    },
             
             
            }
    return rules

```


```python


def Spoken_To_Written(corpus):
    a=get_rules()


    text=corpus.split(' ')

    english=[]
    t=1
    for j in text:
        count=0

        for i in a:

            if j in a[i]:
                if i=='Tuples':
                    t=a[i][j]

                else:    
                    english.append(t*a[i][j])
                    
            if corpus in a['General']:
                english.append(a['General'][corpus])
                    
                return english
                    
   
            elif j not in a[i]:
                count+=1
        if count==4:
            english.append(t*j)
            
    return ''.join(english )       
            
```


```python
Spoken_To_Written('two dollars')

```




    '2$'




```python
Spoken_To_Written('C M')

```




    ['CM']




```python
Spoken_To_Written('Triple A')

```




    'AAA'


