---
id: "e7e27e72-c8ae-4d07-8ec5-c568aa98df17"
title: "Exporting and Importing the Output Configuration"
slug: "exporting-and-importing-the-outputconfiguration"
category: "Output View"
category_path:
  - "Product guides"
  - "Output Management"
  - "Output View"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-11-19T11:51:29.172Z"
modified_at: "2026-01-20T17:24:33.56Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
  - name: "Federica Zani"
    email: "fzani@doxee.com"
source_url: "https://docs.doxee.com/docs/en/exporting-and-importing-the-outputconfiguration"
synced_at: "2026-01-28T20:54:06.226Z"
checksum: "a47bab3bffe197d6"
---

It is possible to export the entire Output configuration in XML format and import it into another project. Often, the Output configurations that enable the production of documents for a consumer are very similar from one project to another. If necessary, you may transfer configurations by exporting and importing them.

> Warning

If you have used attributes from the data schema in the Output configuration you have exported, these attributes may not be available in the project you import it to. After importing, you will have to review the configuration and check that all the attributes used are expressed correctly.

## **Exporting the Output configuration**
- From the **Output settings **exploration panel, click &nbsp;![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABUAAAAXCAIAAABrvZPKAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAACXElEQVQ4jaWTz09TQRDHZ3b37fa1r7XAK0SCkQsHg6QaIzHxjBf1oFXU+Hd5U++ikcSrf4AHFT2opKipDSANFIh9z76Wt7vjoVUeP3yifi87O5PPzM5kFpdqa/AfEgDwdeP7QnW9HWkAOiI2NpIfG/ZG/Zwgog+1rRfvGhPD2btXy8cKbjr57Pn7hU+bn1da506V/GJGAIA2NtYGgHKuk8/KdJ4ztNZ2NcTaEoHoeXNSXLs0OVIqOIIhMmPN/NP55eUVa40xplKpjI+PM8YAaPbKmdgsvP641QPZzwNzrnIE55wzhkCw0dyo17/UarVHc0+azSYicM445wVPKckRYQ/fFyZsAiIiok4UGWMpMVlM2Hv53wgRMJGaEvaR+BQdhceUGAMAIqK0zdkf2t8/IqaVOJjvsP7/KsMh/D9KHHRVq0tBENTr9UajobXu7MTV6pKUcmrqdCaTSePDIASg1dXVxcXFtUbj5as37SiKY33/wcM7t28NDQ16nlcsDiQHuoeXUiLC9PR53/eVUt1OJwxDArx5ozIzM5PPe4iIDJOz2uURQErJGO5oOD568sLF7FagW63wbHmyXJ5yc4Wcl+UMIWV/EQERiYAxrqSSMiNVxssXlFIEyBAZ2z/vfn0LsN1qbwcdzhkCCcH8oYHZ65ctkZLScRxE/Ba2icAainbMr+/U5zeD7r3Hb0+UPCHQGjBkjaXeryNLxgIRaQtEFGuzvh15rtzlyxN+acBlCK4UDIEILBAQEAD1ttsCQP9qrdWGlMP9oqskF4g4Mpj1i26v/z+q93JEYIiM4Q/3tAZrFbxE2wAAAABJRU5ErkJggg==) to export the Output configuration to a file.

- &nbsp;Select the destination folder and the file name in the file selection panel that appears. A notification message confirms the success of the export operation.

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAX0AAAArCAIAAAAbu89YAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAASQElEQVR4nO3cd3hUVdoA8PecW2buZEp6SEgngDRpIXQEKSIqiiDqrrCKhW/FT1dlF8uuyO6CSBQRWFzsDcsqFpQAIgKhSTUkEFIIoaRPepuZe+857/4xSQBZWURYwOf8nnl4Ljf33vPeM8mZ95Q7xO12AwAAcE+jrzDTW5iplx5BUzdry1lDDQiCIPxchMpBEbIrDChVo5JsXQZa4rqd9vOKigoAQM70o1mN6W85kqIDYqJke4AaHKg4HZcoakEQrmSIvqoavbrWbG5uOFzYWFQXetdcarG1/ZyUl5cDgOk+pmd/HTGggzUs+NIFKwjCrw0yXp9zpGhdRvh9C9p2yojIPY1mRb4tkFlDnYDmJQxREIRfGULBkdQ+IDO7af8m29XX+HfKAMDq3UbR/vDhSQCi0REE4QIjMgZdnVS0Lu1ku8M5NxrrsabIEtIHkF3a+ARB+PUhBOxxEUZ5mmmakiQBgMwYM3xe0D0i2REE4aJhCKjrusViIYTIhmHquq4CinZHEISLxgQEj8dDqaQoimwYus/nU4GLEWVBEC4aEwE9Ho/ValUUWdZ13af7HCLfEQThIjIR0evx2O12i8Ui67pu6AYAnmO+gwCASAg5j5Lr670bNuV+vTbL5dR69ojen1WUmBD60PRrzuNSZ1FX7y0odPfpGXP0WNXiVzbFxYY88uDwC1vEhdXQ6MvNL0/uHXsuBxeX1L64eENUZODMR0Ze7MAE4YJBBgC6rhuGiQgyY4xxBv8t3/F6jfStBXNTv9l/oBQRhw5OfOKxUUMGJv6sovMOlzwx+4sAm3rXHckBNumrNVl335VyYfOswqNVqYs2hIXa+/SMrKisW5WWOfU3F7iIC6uouPa5F9a7nNbk3lHncnxNbcOXqzPvmNTncr4pQTiDCQimaTJmAqDMOUeOAHCWSXTT5JvSc6fc/0FCfMjsJ0fX1Xk/XvnDwzNXvrJoYv/kOP8xjHFdZ5qm/OhcxrjPZ9psKgD4vLppsMkTej46YygATBjfnZKzlXsuEIFzjgiyTAGgsqrh2415d0zqBcj69W6f+8OTpxZxLkH+EpyjYTCLRf7RTp/P0LT/fPHqmsZ13x66bULPc60H5IgIyMWiB+FKggwBOOecc0SUpk27V68qcTXnhyTHAvD/+CoodL+waBMAeWPZpPHXd+mfHH1Vp/CS0vqwUFuPbuHHTlQ/+ezq303/KPXlTVu2F8TGuOJinDt2Fk6a8m5RcfUzf1/71Jy0nLwyQD7l/g/L3Q279x3fs+94XKxr3ITX6uubhw6KKy2rnZf67Z33vP/eR3sLjrjnzFtXXdMoy+SGia8bhtm/X/Suvceuv/V1XTcoxRtveyPzQNHMp1d9ufpAWKjtznvef+RPX7z8SvqhnNKwUNusZ1ZnHSzLPFCSfag0Jto5Zvzy2trmYUPii0tqnnp2zdQHPlywaOPG9PzYGGd8rGtfxombJr9ZUlb77Nx1T8xOy8ouHtAvxuFQ2m782ImqGY99ds/vP37zvZ2cmZ06hix9devv//CpYZgx0c6n5qT9df43cTGuxkbvdbe8mpdfsWjZ5of/+EX69oLeV7cLD7OVltU9PWfNlPs/mP/Sxg2bc2NjnAlxgZkHikePX37wUOnjT616aenmrTuOHMguzzxYlpFZNOmWbkXFNTMe/+zu6R+9/u73pmEO6h8DwCurGlNf3njb1HeWv7mjocGbd9jdo2vEyOGJP/V+iZd4XW4vNI2yzQWeTsMCAuw2m01GRAQA4GfJ2+vrmwqPVSclhfToGkYIs9no2NGJY0YlUgLFJdWLlm5ZvebQfVOTZYW+uHhrVVXT269O4mgWHqvatKXggWnJuXmVH32a1bljyD1T+vzrs8zx13cZOSKJc9Ormxx5c7Pn2025b6/YM+XOXsOHJr713r5jx2s4ckTTMBhHE8BENE2TcWSIZlFJ3cYtBddek1hb6331zR2Uwqfv/eZgTvmy13bGx7oGD4gpLq0bMSzx+tGdOJo+3eTIysprF/1jy+dfZU2b0tdmU55fmO6ubFzxxmSO5vETNeu/y5s+rd+Rwpq33t+7Zn32vVOT/XddWt7w0tL0PfuKlr98c0lZw+J/botsF3DrTV02byl4491dQYHqJ59l/t99KaNGxO/PKqtwN27eVjBtSt+xo5OWvPJ96subFvxt7MvLtn7y+f677+rjclrnpm56eOaXH719OwKWlTd8813emBFJXt2MaucoKq4dMSxx7KiO5e7ahUvTt+88tnzxzeXuxkVLt0VFBdx6U7dt3x9e8s9tE2/udvMNXd77KKO+3nf290sQLj/M5/XOnz9f0zRVVWUABEDAs40rezxed2XTgH7RBExAAAACIBEAgNLSmo1bCkYMi58/Z2RtnTcs2Lpw6Y616w6lJEc7HdZRwxOm3N5j2/cnVn55wGalgwckffJZZmS7gBuv67BjdxEAArLa2sa9PxTFRLsefXBAVKRDs9Cde44DMkAG4O9QmKdsM6tFHpwSsyR1HAIgR6/XqKxqzskrt1iopknjrkv65POsyHDbhBs77d5X4j+roqJu/cb8YYPjF/x1VH2DLzxUm5ua/vWa7GuvSXTYLSOHJUy5vceefSUr/pVRV9vUVg9VlQ07dh4dNSJh8oSrCgprtmw9smZ97sTxVz3+/wMmTvl4+sNfDOwf8+iD/QkwAGa1yil92z94X3KFu6moqG7D5iMZmSfWfps7ZGBs6t9GNzbq4aHa7HkbV60+OO66Tqoq9e/bfnHq9QCQdbB8xccZYSHapJuvys2v2rqjcNTw+MkTrjp6vHZTesHqtTmjhyfs3nciPCzgj48MTIgLDgpU13+X31ItgnClQJNQEh4ermlaUVGRjNgyR3WWz0+rhQS6LFXVTW3H6AZrbjYCXVaP11dT642KtFPKgoOU/v0iLRZ69Hh1SnKkIhOnQyGESRKXZco5I4QDAAAnhAH4hye41+ctL29QFRIUqEgSt9sle4DS8nmOiMgATETGOQdgAMyiSuHhNkpZQ6O+el3e8wu3V1Y3JyUGM4aE8NYi8NQifLqvusbTPjKAUhbokgemRNk0ufBYFUCsLBOXUyGEUYkrMmWctd2j1+fLznX/kFn67ocZiEAJDB0UJ8u8c6egOyd1+/yrnJvGdnS5ZAATwFRkEhJsoZRZLNAuQvP5jKPHqquqm0cMjaeUOZ3SwP5RATb5yNEqAKYqUkSEjVIGAIRyACDACWE+3Xco152RWfrBJ1mIQAgMTInRDV9Zab2ikLBQqyQxh11yOS0i3xGuNKaqqlOn/s7pdKamLpAB/B2ts+U79gApur2joLA6O6esa+fQhkb945XZc1/c9uiDKQP6tXc4lLLyBkDTMJjb3eDzmXExTkBGCFCKJ7MVwJah0LYUBhGAWxQIC7Xm5LmPFFZ2Sgo+fqK6sUn3pzYIaOgGoMlMo6nJAOCAjBBUZAA0CwsrF/1jZ7++7f7x4tjde0umTv+KEmwty1+EPztjqgJOp9oaJHe765s9Rnys0x8PlfD0lKqlHlQFO8QHDR0Us3DeKMNkDQ2+kBCbx+Pduu3oB58ciI91vf7uvqGD2/ft2Q6QGQZ3uxsBTUPXK6saVZXGxdhdTktpWT2gaZrc7a5vbjYS4lytt0BaCkKztXJMRcLE+MBBKdGLF4wxTVZX7wsNtdXW+SLb2XTdLC6psdtC6uqa6+q9577uQRAuC2gCEEJaVuDIiG0Nz0/Oj8THO6ZN6XHvQ2kPPJz2m9u6VlQ2v/vBgbAQ25iRcVarMqhf1NoNhc/OT49p73hnRVa7iIDrx8RXVXuhpf/GEBgAIjD/MxrYuu2fjAoJsQwbFP32isxZs78b0C9q5Ze5AIDAVZXIMt2QfrR719BVafmIiMARGBAAAghMN4zKqubaOm/WwbLV3+Q3NRuGyQjlQCAnv3Ltt4eDgqwAiIAhwerQgdGr0g4/M29zYrzr7RVZYaHajWM7NHsM/9/8KUHytnoIClT79o5Yv/HIl2k5ZRVN817YMX1arzsmdln62p7uXUNnzxr8u+mrFy/b9fbyGxB4Y5P+zXeFi5fvUmS6Ki0/pW9kj24hw4fErFyV95e5mzp2CHrr/azgYG38uA6MMSBAiL8SgBAklOQVVK5el9erZ0RK30h/ie4qz5zntj5wT6+nZw4ckBK1ZPme51/afstNnd778KD/zTrL+yUIlxsEDoDYOpwsn9z/05+fFgXGXBvzxpLrnlu4c+afN1ot0vAhMTPu79WpgwsAZj2abDK2aNluzrB/v8g5Tw/qnOTavrMJEAFZayoBgEiAyxIBaNlJCAFEi4rXDIn6+1+GfPjpoazsit/e3mX5W/spxdiYgLt/223Bol2zZm8cc21cxw5BLRcE8F8hqp02flzistczvt9dPGZEfI+uIYcLqiZP6NijS+hXaw57veafZ/YHAoA8KlKb9Ydk0zSX/HOPaWJyn3YL5w3v0sm1N6McAPC0IE/mO+2jtCcf6/enZzzTZqSpqnT7hM53Tuz0zgeZdXW+P/+xf4+uwffc1f2zVfmvvrUvpW9kYKCl99Xha9YXbN1ePDAl6vGH+kRGWGf9IdkwzaXL9xkm69szYtHzw7t2Dsw66P9i2ZaCXA6pd4+wr9ceaWzS166c+NTj/WpqPdNmpCkyve2WTo/N6K0q2L9v2GMP9V20bN/2XcW33tixvDzo7ONxgnDZOf3XlaSnb2nO35tQtSrp/u5nP5EjcoYcETnIMqW0JWVCBM5RN5jXyxwORaKUEEAExjilhFLStk0IOXNndY1389YiWaYdElxdOods31ly1wPrnng0+ff3Xs05Mo4EgBCCgJScdgUAYAw5R0JaDiBAKCWGwXw+ZrMplJ5WnH9xjcfLHHZFkn4ySP+VW+oKgXNkjDOGqipRSjgicvQfxnjLdubBytvvTrt1fNKcJwd4PGaAvbUSADhDw+Qej+Gwq5JECGkpiFAiUeIvwjS5x2vabLIs0R+VKEktwZysCkqQY9vpgnBFYB4zY+7+8rFPOBzOF15IbZtH/+/PZ1EC9OSCuJNJPiEgSaBJoFml1ul6IARk+eQBbdtn7tQ00tysP/LEluTe4b16hO7aWx4caBmQEg5gUgqU/jgM+ZRFeZIEkvTjA1QVVJX6Izy1OP/B1nMI8ke31loEA/8sXmtIEm3bZgBICKoqquop12+N0GqR/XvOLIgQUBRQFOo/68wS/U6rijPqRBAueyb4Rz0Q4Rz7WRdVgAbjxkRzPiht/fEDhyp7XR1yyw3xvboFXkH9iCCXNPKa9oFO+QqKWRD+p05fXi+jf5z3kj6PHhIsTbkj4beTEwCQEEIpIeRK+gOOjdaWLBgAAGJuWxB+AoNTBpbllg38pc9J/UKUAG3pXGDbP1cK4u9zwRUWtiD872BLu+PPLeTWFkisQxME4eJpaXcsFutzz82/9OM7giD8+iFv25RlWW7rZYl8RxCEi4ZD6/gOIv6MeXRBEITzdXq707pX9LMEQbhYEFBX7W3/lRHRpGoDBHrKfFq7MxbhCYIg/DLIwVPBmi0hp/WzDMlSg6FNx45qEZZLHaEgCL82yKAuz6h1xJBT+1m6rFVA++rcAldXQ7GLp34EQbhwELxVvCBDq4xNCAMCQBBBJoQAlWrUkJ3VnaV1OdHDqSVYND2CIFwAyKGpmOen0Uy1u4W2PUyOsv+5BJOqRzCyLNscduJI0jA9sBuRVNH6CIJwvhCMJqz4Hg9us21WuwUEB1oJJYRQShFRliRZkhRZlomslpGgNTVJ3VeVx6+qUgj/75cWBEH4TxDAi0o2ROZABEiaJCuyrMiyIkkyIsiSJKmqarFYVdUiq5Ya5tjMtC0Qd6nDFgThiseBSIrqsFg0zappVqvV2pLvKIqsaVa7PcDrdRiGj3Pu8wHjvGU5oSAIwnkhhEiSpGlWh8Nut9sDAgIsFlWSKADKsqxomuZwOAzDNE3GOVBKfT6faZqi6REE4fwQQhRFsVo1h8MRGBjkdLo0zaYoKqUSIsiUUkVRbbYAxjgAyLLU2Gj1er3+dkc0PYIg/Fz+8WNFaclpgoKCHA6HpmmyLANAy/odWZatVisAtB3q9frzHdHbEgThZyOEEEJVVdU0q93usNvtNptNVVVJktq+5xQpJaqqUEokiaqqYrNpPp/PMAzOxZSWIAjnwz9hZW3lb3TavhlPbk1oiCTJViuVZcVq1UzTZIyJdkcQhPNDKZVlWVEUWZYlSaKUntp3+jdWjX8jD1CBUwAAAABJRU5ErkJggg==)

## **Importing the Output configuration**
- From the **Output settings **exploration panel, click &nbsp;![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABUAAAAXCAIAAABrvZPKAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAACbklEQVQ4jaVTW0tUURRea9/mnH3OGZ2DI5hFZDTjCELSS5D5VlMvXUB6CP9cf6GeBQlfhmaSUNAmGAlDwQSz5uZ4zlo9jI4zx0tK39Pem+/b37pidXMH/gOKmb9826ts/JQIUuCQpwUgARMxAxMDETABATMDAcRx3DqktNXZjPtwekwBwO5+a3u3vvBsMptxRzK+koIHTbjv1O4cfVhcX/t+0DyMHhRGFQAwMzM7KeW52nO1UvKSgLVCLQURxzEzgOq+IkCYtiMZH6SMiIF4/+B3HEcfl0sTd27n7k04qRQiEPBQ4DopiXiSf+9jFCiE8K1h5q2trZXPK81Ws7S8vLTYfjM/P/v4kXVdrTUgosCeSsEgoiiqVMqrq2ufyuVms1kqleuNZq1WW/jxNgzDubnZbHa0rx4gEvp2u22tl8/ngyBIGVMo5FzXefXyxeRkfnz8RhRFzASn9mf8mVkIYYyRQgghUsYIIXzfN8YopbjnfDb/LoIgmJoqdDpHlUrFWus4jrNRzedyMzP3tdZSSkTs5yf1iKiUBkCllFJKSokIWitjjNYaAIiony+6McO1wKcjJQAAAS9jA0KC0HcTiftVcSJJ9u88cP8GJHAVPSTrk8j/Yl9mYGDARILnzg8xEcfHBETPs0ErYOJi8UkYhr22xzQQzvn+iIAourDWSjm40X36Y/9GJ3q/uB446nVxOjPkMsPT4nOKiZiYwfe8VjtCjLq1qO02DqPjKVKIeGs0yA7b6nYdAb6+K0nxj6L+qrfv3hweG7FGS6xu7vxpdLb3GkcRXdymJNK+cVIyTDtY3dxh5piuN8KIiABC4F+qOPoZFCUkDwAAAABJRU5ErkJggg==) to import the Output configuration from a file.

- &nbsp;Select the file in the file selection panel that appears, or click **Cancel **to abort the operation. A notification message confirms the success of the import operation.

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAX0AAAAqCAIAAADQ5xz9AAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAARbklEQVR4nO3ceXRURboA8K/qbn073dkTSMhOBFmCQRJIXBAFERBRFHAFFbczOqNPZZ7bvFHnjBsoRlAYVNQRUVxwFCSAIPu+CQlLyEJYsneSztrLvbfqe390CEQREWEAT/1OH87ldnXVd7uT6q+WG+JyuQAAALi3xV+a5yvNMyoPoGVYDdWs2Q2CIAi/FaFyWCc5JAooVWNT7T2ytcReHZ6vqakBAOTMOJjfsuZDZ2pcUHys7AhSw0OVYOc5iloQhAsZor/ObdQ3WB5Pc3FpS1lj5F0vUc3e/jyprq4GAMt1yNj7Xaesrrao8HMXrCAIfzTIeFPBgbKlO6Pvn9x+UkZE7m2xaorsocwWGQxoncMQBUH4gyEUnKldgvL2tu5aZe9zVeCkDACsyWWW7YoelAogOh1BEM4wImNYn9SypbnH+h3OudnShO4yLeJSQHZu4xME4Y+HEHAkdjKrcy3LkiQJAGTGmOn3geEVyY4gCGcNQ0DDMDRNI4TIpmkZhqECin5HEISzxgIEr9dLqaQoimyaht/vV4GLGWVBEM4aCwG9Xq/NZlMUWTYMw2/4nSLfEQThLLIQ0ef1OhwOTdNkwzBMwwTAU8x3EAAQCSGn0XJTk++HVfu/W5IfEqxfkha3K78sJTnyzw9ddRpVnURjk6+k1HXpJfEHD9VNm7kqMSHisYcHndkmftWRMvebb6+I7xL2+F+uOWGB5hb//qLqjL4Jp1JbeUXDG9N+iI0JnfTY4DMapiD8tyADAMMwTNNCBJkxxjiDX8t3fD5zzbqSl6Z8v2t3JSJeeXnK008MuSI75Tc1XVhc8fTz3wTZ1btuywiySwsX599zV/8zm2eVHqybkvNDVKTj0ktiamobF+TmTbjjDDdxKurqmxbk5t8+9tITNn2krOGVN5aFBtsy+saeSm317uZvF+XdNubEtQnChcACBMuyGLMAUOacI0cAOMkiumXxVWv2j3/g0+SkiOefubax0ff5/B8fnTR/Zs4tAzISA2UY44bBdF35yWsZ436/ZberAOD3GZbJxo2+5PFHrgSA0aN6U3Kydk8FInDOEUGWKQDU1jUvX1l425h0QJbZt8v+H585volTCfLUcY6myTRNPuGTiAjAA03/JEi3u/n75QVjR/c51WtHhoiAXGx0EC5UyBCAc845R0Rp4sT7jLqKEE9RREYCAD/ho6TU9XrOKgAye8aYUcN7DMiIu7hbdEVlU1SkPa1X9KEj9c+8sOjuh+ZNeWvV2g0lCfEhifHBGzeXjhn/cVl5/d//ueTZF3MLCqsA+fgHPqt2NW/dcXjbjsOJCSEjRr/X1OS58rLEyqqGl6csv/3eT+bM215ywPXiy0vr3S2yTK6/5X3TtAZkxm3Zfmj4ze8bhkkpjhw7O2932aTnFny7aHdUpP32ez957H+/eWvmmn0FlVGR9qf+vih/T1Xe7oq9+yrj44KHjprV0OAZeEVSeYX72RcWT3jws8k5K1euKUqID05KCNmx88gN4z6oqGp44aWlTz+fm7+3PCsz3ulU2i/8x11Hht74rt9vZPeP35lXNuSGWT6fX9elYaPf3V9YkzNj9aN//WbtxpL0Pp2jo+yu2ubJb64Yd/fH7324qbnZW1RSm9ar05XZiRu3HBw7/t+P/vWbnHdW5++piIt1TnpuYf6eqrw9VTvzysbc1Kus3P3Ik1/f89C82R9vsiwre0A8AK+ta5ny1oqxEz6e9cHG5hZfYbErrWenwYNSfukzEg/xOJ8faJlVq0u83QYGBTnsdruMiAgAwE+Swzc1tZYeqk9NjUjrGUUIs9vpsGtThg5JoQTKK+pz3l67aPG++ydkyAp9Y9q6urrWj94dw9EqPVS3am3JgxMz9hfWzvsqv/tFEfeOv/SLr/NGDe8x+OpUzi2fYXHkHo93+ar9H83dNv729EFXpnw4Z8ehw26OHNEyTcbRArAQLctiHBmiVVbRuHJtyTVXpTQ0+N79YCOl8NWcO/YUVM94b3NSQsjlWfHllY1XD0wZfm03jpbfsDiyquqGnHfW/mdh/sTx/ex25bWpa1y1LXNnj+NoHT7iXrai8KGJmQdK3R9+sn3xsr33Tcg41kcjM03G+dEYGOPIEFh1Tcvq9SUTx/e7bkjq27M2vT5t1cw3b1y7oXjGexvH3NR75LDuc+btbGryAfDyyvo3315tmuyrT+4oLK6dOn1danLYFdkJh4+4Bw1MGTbkompXw9S312zcfGjWtBura1pyZqyPiQm6+YZe6zcVT//XhjE39Ro1oseceTubmvwn/4wE4fzG/D7fq6++quu6qqoyAAIg4Mnmlb1en6u2NSszjoAFCABAACQCAFBZ6V65tuTqgUmvvji4odEXFW6b+vbGJUv39c+IC3bahgxKHn9r2vpNR+Z/u9tuo5dnpX75dV5M56CR13XduLUMAAFZQ0PL9h/L4uNCHn84KzbGqWt087bDgAyQAQQGF9Zxx8ymyZf3j58+ZQQCIEefz6yt8xQUVmsa1XVpxHWpX/4nPybaPnpkt607KgKvqqlpXLayaODlSZP/MaSp2R8dqb80Zc13i/dec1WK06ENHpg8/ta0bTsq5n6xs7GhtcP7gFaHGNoGO5Zuk/v36/Lw/Rk1rtay8oaVq0v3FVRs23EkprNz0l+ykxJDQ5zKD6tKAHlivPPzj8b6fGZ9vbfkgMtmk1SVXD/s4k+/2BUVoY+58eL9RXXrNpYOHpQ8bvTFpYcaVq0tWbSk4NpByVt3HOkUHTTp0ezkxPCwEHXZiqK2MAThQoQWoSQ6OlrX9bKyMhmxbY3qJN+lNo2Ehmh19a3tZQyTeTxmaIjN6/O7G3yxMQ5KWXiYMiAzRtPowcP1/TNiFJkEOxVCmCRxWaacM0I4AABwQhhAYKqC+/y+6upmVSFhoYokcYdDcgQpbd/tiIgMwEJknHMABsA0VYqOtlPKmluMRUsLX5u6obbek5oSzhgSwo82gcc34Tf89W5vl5ggSlloiJzdP9auy6WH6gASZJmEBCuEMCpxRaaMs47vAwNABAZgIVjtMcgKjQjXKGWaBp2jdb9hHjpcX1XVpCokMlKTJO5wyiHBGgD3tHoWLyt++fV11a7Wi7tFMoZAApePBDghzG/49+137cyr/PTLPEQgBLL7xxumv6qySVFIVKRNkpjDIQVqE/mOcMGyVFWdMOHu4ODgKVMmywCBgdbJ8h1HkBTXxVlSWr+3oKpn98jmFuPz+XtfemP94w/3z8rs4nQqVdXNgJZpMper2e+3EuODARkhQCkey1YA26ZFj08fgGsKREXaCgpdB0pru6WGHz5S39JqBFIbBDQNE9BiltnaagJwQEYIKjIAWqWltTnvbM7s1/mdN4Zt3V4x4aGFlODRtgJNBLIzpioQHKweDZK7XE0er5mUEByIh0rYMaXq0O8gomlYgBazrJZWExABmWkwl6sF0DINf21dq6rSxARH5872rTusigq3wx7R1Nja2OQDxMNl7tenbezTO+q96ffk7a4ZM+Fr6ViQCGgpEqYkhV4+IO6t14ZaFmts8kdG2hsa/TGd7YbfKj++tlPe6yAI5x20AAghbTtwZMT2jucX10qSkpwTx6fd9+fcBx/NvWNsz5paz8ef7o6KsA8dnGizKZdlxi75ofSFV9fEd3H+e25+505Bw4cm1dX7oG38xvBY1sACI7rAcWCdJyJCG3hZ3Edz8556fkVWZuz8b/cDAAJXVSLL9Ic1B3v3jFyQW4SICByBAQEggMAM06yt8zQ0+vL3VC36vqjVY5oWI5QDgYKi2iXLi8PCbACIgBHh6pXZcQtyi//+8uqUpJCP5uZHReojh3X1eM3A7/9xQfLj3wdFAU2Vlq8uTb8k6rvFxYg8UKCl1fh+Rem0WVtkiS5cXDQgI7ZH9/CsjJiZs3dMfmvjDcNT58zbE6jNNE1XXWtMk33PvuqFiws9HiMQJKWksKR20dLC9Es69e8X8/3K0m9zC1y1nn+8tv6Be9Kfm5Sd1T92+rvbJr+54caR3ebM2x34gE7yGQnC+QyBAyAenU6Wj53/5e9STYGh18TPnn7dK1M3T/rbSpsmDboi/pEH0rt1DQGApx7PsBjLmbGVMxyQGfPic5d1Tw3ZsLk1kBocTSUAEAlwWSIAbScJIYCoqXjVFbH//L8rPvtqX/7emjtv7THrw12UYkJ80D139pqcs+Wp51cOvSbxoq5hbRUCBGqI7ayPGpEy4/2dm7aWD706Ka1nRHFJ3bjRF6X1iFy4uNjns/42aQAQAOSxMfpT/5NhWdb0f22zLMy4tPPUlwf16BayfWc1AGCHIDvkO11i7BMn9H7ljc1PPrvi+uuSu6eGBxKxsFAtvU/04mUl6zaUZw+IfeKRvpqKWZnRjz3Ud9qsHzdsLh81omuNqwWAd4rSbrkhddqsH7dsrxxxbXJ6WlRhcV2Is0d6WtR3Sw60tBpL5t/y7JOZ7gbvxEdyFYWOu6n7E4/0VRUc0C/qiYf75czcsX5L+eiRqdXVLSefgxOE81rHH12yZs1aT9H25LoFqQ/0PvkLOSJnyBGRgyxTSttSJkTgHA2T+XzM6VQkSgkBRGCMU0ooJe3HhJCfn6x3+1avK5Nl2jU5pEf3iA2bK+56cOnTj2f86b4+nCPjSAAIIQhISYcaAIAx5BwJaStAgFBKTJP5/cxuVyjt0Fxgu43Xx5wORZJ+MchAzceu+vgYECklu3bX3nZv7s2jUl98JsvrtYIcbZf888KEEomSQJBAgB4XpGVxr8+y22VZooHYGOOMoapKkkRO2HSgtjP2cyAI/0XMa+18aVf1sKedzuDXX5/Svo7+6/dnUQL02Ba5Ywk/ISBJoEug26Sjy/VACMjysQLtxz8/qevE4zEee3ptRt/o9LTILdurw0O1rP7RABalQOlPw5CP26YnSSBJPy2gqqCqNBDh8c0FCttOIcgOV32CGBgAEIKqiqp6rLZfKHziIBUFFIUGXtseW3vlJ6lNEC5MFgRmPRDhFMdZZ1WQDiOGxnF+We6yw7v31ab3ibjp+qT0XqHn7ZgiLEQafFVsaLB83kYoCOedjlvtZQzM857T+9EjwqXxtyXfOS4ZAAkhlBJCzt9f6cR4ffrkLAAQq9qCcMoCNwy1ja/ktgP8vfdJ/U6UAG0baGD7P+cnAiAFhj/ncZCCcH5pu1ERA7mFfLQHEnvSBEE4e9r6HU2zvfLKq+d+fkcQhD8+5O2HsizL7aMske8IgnDWcDg6v4OIv2EdXRAE4XR17HeOnhXjLEEQzhYENFRH+39lRLSo2gyh3iq/3vln+9sEQRB+H+TgrWEeLaLDOMuUNDdGth46qHfSznWEgiD80SCDxkKzwRlPjh9nGbJeA13q95eE9DQVh7gDSBCEMwfBV8dLduq1CclRQAAIIsiEEKCSW43YXN9dWloQN4hq4aLrEQThDEAOreW8KJfmqb012n4zOcqB+xIsqh7AmKq91sAjB1IHGqG9iKSK3kcQhNOFYLZizSbcs96+Wu0VFB5qI5QQQilFRFmSZElSZFkmslpFwha7U3svqE5aUKcQ/utVC4IgnAgC+FDZCzEF0AkkXZIVWVZkWZEkGRFkSZJUVdU0m6pqsqq5mXM109dC4rkOWxCECx4HIimqU9N03abrNpvN1pbvKIqs6zaHI8jnc5qmn3Pu9wPjvG07oSAIwmkhhEiSpOs2p9PhcDiCgoI0TZUkCoCyLCu6rjudTtO0LItxDpRSv99vWZboegRBOD2EEEVRbDbd6XSGhoYFB4foul1RVEolRJAppYqi2u1BjHEAkGWppcXm8/kC/Y7oegRB+K0C88eK0pbThIWFOZ1OXddlWQaAtv07sizbbDYAaC/q8wXyHTHaEgThNyOEEEJVVdV1m8PhdDgcdrtdVVVJktr/zilSSlRVoZRIElVVxW7X/X6/aZqciyUtQRBOR2DBynZUoNNp/1t5/w/B0nOcv5raGQAAAABJRU5ErkJggg==) 

If the import operation cannot be completed, an error notification is displayed:

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAXsAAAApCAIAAABbbR4UAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAUK0lEQVR4nO2dd3yURfrAn5m37L7bsumNkARC7yQhhBoIKNIUUFBAPD3PO6xYUX+ecp4cqKDIgYKHAoKe3llBQpEWmiAlIRhqCoRA2ia7KZtt78z8/ng3YSlG5fA4Zb5/5DMzO/M8zzx599lnSjaoqqoKAKirwVOc5y7O85YVMdWrOipIvR04HA7n54KwGBwpBoUDxnJMkqFTui6+y4UXKysrGSXe00cadiw3J7UyxsWIJqMcYpUs5utoM4fD+bXCmKfa7q1xqI2N9QXFDaW1YVNnY51BexFVVFSoVWe8R7+O7NtWHx5yfU3lcDi/JRihdceLSjfmRtz/mtYiksZ6tfKUwUr0YRZg6vW1j8Ph/JZAGMxJsca8o87D2w3dBwOASOqqfKWHIzKSAHi44XA41xgksuDuSaUbs/wRx9dQx+ylutDewMj1to3D4fzWQAhM8ZG+iixVVQVBEH0eN3hdPMHhcDi/GIQB83q9Op1O9Hq9MjAecTgczi+GCgxcLhfGgujxeGSgfM+Yw+H8YqgMmMvl0uv1osfrMfMch8Ph/IKojDG3y2UymUSf1wfArnuOU3TatmhJdpuEsIf/NPiqhZw+U73wne0J8aGPTs/QyvGtQx97MOOqBdbVu08VVib3bF1y1r5g8dbWcSEzHhpy1dKuDqfTu23HyS/X5ioGOS018VBOSUy09anHMq+5lqPHy1KT48sr6l5785uoSMszjw+/tio4Ny6MAIDX6/X5VJFQAi3mOLu/Lbp96vLAlohw0wP39XvogYHX0KTKSsfa9Ud+N6XPf5JtVdlqv17//ZQ7kwHUSlvtmqy8aZOvXuCZkppX39gcEmJM7hlTXVO74Zv8P9zb77+fDJaUVj31/OeSLEyZmBwarPti7eGpk5KvrRll5XWvvLrRaJRTk2PtjvrP1+Tedcc1VsG5sVGBgaqqhKgiowwAWjgaZ4wqeql3z9i01PjmxrBQw088TSeEer1EUaSWuzFGGWPAaLPYKw5kDCiljIEo4itJ0YQwYCS1V+yJnOcwgkCBHo9qMMg/xWwAqK6u/2briYkTegIjwChjAIwS1edy+Uwm3U8U0mQ2o5QJwkU2U8rcbt/l9lzS7vN6G13eeyekznw8AwAV5D2PUEu/r59mz0VurK11rv/m2IRbuwEjndqHFeb9X6CKFux0ubxG489zBedGhBEGQCmllIqMsZZzHAACiMXHBT35yIDmJoRgz77CR576MrV33PadhR3bRzw6vf/TL6xrrv5z+eQqm3PuG9s+/uwwIbR/34TnnhwysF/i3v0lDz7+RVpK3LYdhe2Twj9ZOaUppmjPNwVQz5Y65ryx/eNPc4lK09Pin39q6KD+iV4v2b339NMvrDuSX240ymNHdp43e1RYqLG8sv7vS/YsfX9vWIhx6OAkAAZAANSDOaXTHvh48h29brmpw58e+3zULZ22bC/IP1oxakTH114eGR1tqahsWLhk97vv742IMI0c3nHXt8VjR3V+7smh2gRPFtieeO6r0yX2d5btOX2m5qlHBwKwUwUVmaPePnK0YsKtXefNHmWx6EtKHc/PWr9m3bHISNND96fPePjSvK/0fO2s2Zs+/ep7AePbRnd+5cWbo6MsZRX1c+dvW/1JjtdL+iS3euGZzCGD2h7JL5/2wMfjxnbdsr3g8JGyEcPavzFnjN3huvm2d23VjQuX7Ny7//Qbc8ZMmPLBxPE9Xn7hJlt146Kluxf/49uQYGXcmK7bsgtGj+g04bZut09d9bupKc/MyDh2onLClA/umZI8dmSXO+5eNXRw0uZtp4KtyuyXRjz74vqcvPOKXrops93MxzOe+XNWyVnHshX7ioqr//bSiDGTlt9xW/fZL42osjnnzN+28qODHo+a3DP2xWeHZWYknSyw3T71g4nje2zJLjiUc27YkKSFr98aGxN0LR9Qzm8Nf3hhDEQGoL3Pf7g3AYDz5bXLV+3T6gaD1L1rFKNqSanD7fZlDm4TGWnW6VBgtcZR/+biXWvXH7t/Wook43lv7bJVO1cuncCYevacw+3xZQ5uExFhUhTUpFoFYAD0fLn9zcU7167L//20ZL1OfG3BTputYdWyO0RRWPjOTozh01WT849XvPOPfZ9+kXvP1N7ZO08tW7HvzvHdbh7W7oN/5tbVe7QASpnq8aqUEcrUM2ftm7edfODe1MKimhUf5qzffPSu23ts23Fy2Yp9Uyb1GJaRtHz1oeIzdkYv+CHIIvbvG1d6zp4xqM0tw9sDkIqq+i3ZhbOeH1pQWP3+6oPrNiYMGdT2zUXZ3x04u3ThrWXl9QuX7o6KNt45oXuz4yqqGhYs3rlle8HsF4fX1rkXLd1rteqffWLQW4t3ffLZ4d9N7mW16l95bfsjT3358co7GWOl52uzNh578A9pJWdrl7z33dcb8ifc2uWP9/V5f9WBsSM7DR3cljLV7VEpJW63e+fuU4uW7rnz9m6jRnRYsTqn6HQNpYQx1ecjlBIAlTFVVQmllDG1sqoha9OxEcPa19hdi9/d7XR5P109ueh0zZx52R3bhw3qH19UXD1kUJubhrWjTPV4VEpJjb1+4Tu7Vn98aNpdPSPCjbP+tnX6jM8/+3CyLItlFfVffv39o9PTb85MWrB4z5qsI9Pv73vNH1LObwjicbvnzp2rKIoIoC1DfjjiMOJwuD/7Kn9N1nGtoUe3qHffGgtAFJ04ML313+eNBIBv958NrObklW3bUTBkUMLcv2Q6at1hIcr8v+9Zv/F4elqcohMH9I3Tul3Qy7TtJFpR7tiaXZAxMOHVvwyrrXOHhSqvLdiVteHYE4/0//cHE91un6268fjJClkn1NU31tY6D+aWtoq1PPFw3/jWVqNB2LG7GBgBpvoFMgqMmE26zEGJd0/qtv/QuY/+fdjhaKytdR44dDY2xvLEw31joy0mo7B772kA0mxPZLh+3JiOn3yWFxlmGD+mQ25eeWiwMml8lzsndD6Qc/791Qft9oaamro9e09nZiROHNexsNi+Y1fR+o3H7xzfudlz9pqGPXtPDx6QMP33ybV17tTe0d06R9psdRs2nxiQ3vr1V4Y3NHgjwpQXZ29buy5/1M0dTAZ56MDEuyd1y8uvWL76oMPhDA2Wbxvd4f1VB8JClXGj239/rFLzUkND474DJRHhxqcf69cqJig4SLc1uxCgaU3KaJMHtDKRJSG1V+zC125hAIwyt1u1O1ynz1Tr9QLG7I5xXVZ8eCg0WD9pXKfjJ22aCru9fu36Y31TW82ffVNjoy8q3PD0nzd9sebIpAndDHppyMCEuyd1O3Gqesl7++x253U/eeD8T8NUhFFERISiKCIw+LFVlWoNku+Z0u31v/oPLxACjPGefWd1OiE8XMFYe7JJYNXt9tgd7tgoI8YkJFjqmxqt0+Hikpr0tBhZJ0SEG/yjLuBfVbk9HrvDFRNtwpgEW6W+qdF6vVBcUtPgbFy34eSrb+6x1TQmtQmhhAIwj8dTUVEvSzgsTCcI1GwWgyy6ppSteZlGRBEFWSSECMZMEjElqsfrKa+ok0QUYpUFgZpMgskoX+IHjAgAAGIIEQAiijjYKiNEMKaiiAglbo/n6ImqnLyy1Z8cZgwwgv7prQMleDye8oqGPikx2lyGZcQjBOWVtbaaxowB8RgTi0VIT4s1GsTC4moAVRRRUJCEEBEw1ewEUP1mANXM0Mper6esvE4SISRYEgRiMmGzSdImC8AYIwAqA5UQrUUVJRwZacCYNLp8m7YU/vXVnefLG7p2CieEIkSvqMLn81bZnP3T4jAmJhPunx5rNskFxdUARBDAGqS5gkgiJoTwbWZOi6iyLE+bdo/FYhGZFnFazHEAAAMTBRrQSoERjEESUdNYgtCFqk4Gs1kqr6wHpvp8pKqqzuNRE+LMwAhGIAlwqUZGgDFgVCeB2SyXV9QBU30+WlVV53arCXGWomLbgrf3pSZHLZ4/Yv/B89P+tFbATCdDVKSSl+87X+YwKiG1Dmdtnds/HaYCAwACjCAEGDc1AgNgOomFhymHv/cWFtk6tA85U1LT4PT4k6ML+NOugIEX5Q6yCG0Tggekt3pzznCfSurrPaGhhkAJsgwR4UpNTSMw9VxZ/bKVud27RCS1DbZadOfL64Cpqkqrquqcjb428UGaWMFvp6aaXZyqNJWBSiKLDFdcbrWgwNalU9iZM9X1DV4tnWGM+bw+YCpV1QanF4D5fS4iYGpZmWPuG7s7dQjZu/We4ydsoyf9S0DsUnUMAKgosGCr/lxZLTBVJbSqqq6+wdM24Yp28huknBZhKgBCCCEE2s4xMPjhsyqgAFB6vm7h0u+aG1vFmCPCDQAAiDWNpQhdqIaH6/v1idmwuXjW3B1xrcwrPzwSFWG85abE2loPAAC+XCPVjlDCwvX902KzNhW+NCc7oXXQig+PRIQbRt6c6Gz02aobHbXuI/nl6zadanT6fCqxBkl9kqOXrcyd99a3I4a3WfVxPgBjQBgQ5hfIGFDmXzqSJi0kOFjOGNBq2crcp1/cMjC91adfnoALffwgRBGGE6dsWZtORUUaNVcwIP48AqjVKqX0jtq0teirrOMVlc7Z87594N6eLz3bv1lCsFXqmxrz+dqT8xd92+hS31t1+NaR7fr2ic4YGPfZlydeeGV7h3Yhy1flhYbox45qS0izwYT5VZCAMvOrZowBtQSJQwe3Xrzs4FN/3pw5OP7fX5zQTBIlZjCIm7OL0/pEZ20sZKxZGiAMDIhPVauqneFh+qPHK9auL3A6fT6VAKICRgVF1WvXn2jbJlhTFxQkDRsS/9G/jj7/8rYuncKWr84LCtKNG9NOkxZgZ7NbOJwr438zMsYYiP6Wlj6jSIPTuyW7ZOuOEq1uMkrjxyaNG90OAC58vjV9/GrVuBjDzBmpRCUL3t5PCUtLiZ71XL+O7YL2HSjzHyddqpEghIDRVtHKzBkpRCUL3zmgEtYnOWreK4M6tgsqq2gYc0ubd97L3bv/3E1DErp2Di0orNbJrH9a5PTf93x7We6e787dMjyxuqZR25ZCjABqTg3YxVsbTJbYgPToObMGfvivozl55Xff1WnRuzkIXfRZbbVI3TuHrdtY6HL5/vpC/6ZdIRWAYoQAaEy08twTqXZH430PZcmSMHF8hxnTewZKiAzXzXiwV1W186W/7ZIl4bZRbZ+ZkRwVoZs5I0X1kcXvHvKppHePyAVzh3TuYD2SX+V3Y4CdwFQEVBSw32OMIATAmCyytJSI+bMzVn70/d795+6d2uX1hfsRZlER+j/e1+PluXseefqbcaOTOrYP0e4KaJkOMDUsRJo4rv2biw8eyCkfPaJtSs/IE6dsZhNO7hnxVVZBbb1n0bxMQAgYDQuRZj6W4vOqS97L8XhJj67hi+dldu0UfLLADnDJVtH1v0HK+Z8m4PFAG95bkFi9JukPXX+wMwOVBK6nAAEghDBGhFCMEcZI6xZYBf+lD+b1EbebmM2SgDFCV+jW3Lm5XRvo8xFXwEAAIIRRyhAChBADhgAJAgIAQhmlTLOKMdYsRBOIEAqUrJUdtZ5tO88KGLdNDOrcMXT/ofI77smaOSPl4Qd6BJrkU6nHrSoGUcD4ciHNphJCCWGyLGj2XDKvwA5YQEhbhxDmU6nL5TObZEFACF0qtoUywqih3rs5uwQj1CYxqGunsO+P2kZM+HLmjJQZD/ailBHNGxgxypo9gFCAuwgDBLjJjVhAqo+6XKrBIAoC1lQIGGk+V1XqbPRZzD9i51U8h5wbBOJSc2cfrhjxrNls0U7HW9o5Rggk8covieJF3cSLuyEEggCKAIpeAKAA9IrdLh+uDRQE0AcMBPA3Xo6AQbjsPmCgwEDJWlmvB69XffDJ7JQeEb17hn13sDLIIvdLiwj0A0IgSyBLWLPhciGBpgIAXGllccUOqGkuep3YPLtLxLZc1ukAAbv3wc29e4T3SYk8cKjSYpYHpEcCqBgDbvZGUyHQ51d0lySBdNlMoclO3U+wk8P5YVTwbw2wn7Kq+g1i0MOIzJi35vbL2lRy5Kite9eQW0fG9+oW/Gvxg14HmYOjFs8fuHbDmcNHqjq2t86c0SO5R8ivxX7OjUXAFXkRfvzO8W+TYKswdWLi5NsTAZi2SETo1+SEIAu+a0L8pHHxmv0Iw6/Lfs6NBIGmrWPRH3BuyK8cxQiwf73Dmn/8ivi128+5UWD+iAPAtNPxlv/KgcPhcP4T/BFHp9PfoPs4HA7nvwe7cNgt+i+b8hyHw+H8UlC4sI8DwCMOh8P5JQmIOADAV1UcDueXgwHzyiatLKpYrgerq9yjRF3pdh2Hw+H8BzAKrkrSqAv15zg+QWdnYc4zp5VI/vWRHA7nGsMI1J70OcxxSIs4XlGphNiaE4VBnX2Sif91DIfDuXYwcFfTwlzF1joxHBAAEgELdjl0X00HYePxVhlYF8KDDofDuQYwCs5z9FQWzpO76jDGGCEEIsZIxXIRiy4/qg46W5Q0yGvtggSZxx0Oh3O1MPA5WeVelr/bkC13MYZY9QgjhDDGoiBIoigiUS5HwevtSV3XVCSsqZYQ/XGhHA6HcyUYgJtJRyH6OESCoAiiJIqSKEqCIIqyLOt0elnWibLOTszZRNkJ8T8uksPhcFqEAhIk2azTKYpeUfR6vR5jLCqK3mQyut1mn89DKfV4gFCqfRUph8PhXB0IIUEQFEVvNptMJpPRaNTpZEHAoqIoZrPZ59P+txFgjD0ej6qqPOhwOJyrAyEkSZJer5jNZqs12GIJUhSDJMkYC6IkyQaDkRAKAKIoNDTo3W63FnF40OFwOD8XbYdYkiQtmwkODjabzYqiiKIIAKIoinq9HgCaO7ndWo7D11YcDudngxBCCMuyrCh6k8lsMpkMBoMsy4IgMMb+H3JL2lXpwADOAAAAAElFTkSuQmCC) 

> Warning

If you import a partial configuration or manually make changes to the XML file, this may enter a non-valid configuration in Document Composition. In this case, the current configuration will be replaced with an empty configuration.

The import configuration feature checks that the loaded XML is syntactically correct and the root element is a well known element, otherwise the new configuration is discarded.

## **Sample Output configuration file**
Download the attached XML file for an example of the Output configuration file: [SampleOutputConfiguration.xml](https://code.doxee.com/confluence/download/attachments/28037152/SampleOutputConfiguration.xml?version=2&amp;modificationDate=1594308260041&amp;api=v2).

### xml file code
`&lt;buildconfig previewTarget="DEFAULT" version="2.7.0"&gt;
  &lt;generalConfiguration rendererType="embedded"&gt;
    &lt;postProcessing enablePostProcessing="true" pageDatasectionName="" spoolInputFilename="" pagePositionInInputFile="" isFill="" inputPageAttribute1="" inputPageAttribute2="" inputPageAttribute3="" inputPageAttribute4="" inputType="AFPDS" enableExternalPages="false" externalPagesDatasectionName="" pagesRotation="none"&gt;
      &lt;advancedSettings&gt;
        &lt;advancedSetting outputFormat="AFPDS"/&gt;
        &lt;advancedSetting outputFormat="MMD"/&gt;
        &lt;advancedSetting outputFormat="FORMDEF"/&gt;
        &lt;advancedSetting outputFormat="NAS"/&gt;
        &lt;advancedSetting outputFormat="PDF"/&gt;
      &lt;/advancedSettings&gt;
    &lt;/postProcessing&gt;
  &lt;/generalConfiguration&gt;
  &lt;targets shapesGeneration="blocks" spacingCompat0="true"&gt;
    &lt;target name="DEFAULT" id="DEFAULT" scriptResolution="300" scriptColorModel="cmyk" bwAreaSolid="false" imagesDestinationResolution="300" colorImagesDestinationFormat="jpg" monochromeImagesDestinationFormat="tif" jpegQuality="0" codepage="Cp1252" country="IT" compressColorTIFF="true" spoolFormatAfp="true" spoolFormatPdf="true" spoolFormatRaster="false" spoolFormatPcl="false" spoolFormatPs="false" spoolFormatExcel="false" spoolFormatEmail="false" spoolFormatHtml="false" spoolFormatInteractiveCommunication="false" includePdfAction="convert" fitToPage="false" allTextToBlack="false" forceExtImageResolution="false" gsubst="replace" spoolFormatCsv="false"&gt;
      &lt;fonts&gt;
        &lt;family name="Arial" font-family=""&gt;
          &lt;bolditalic embed="true" filename="arialbi.ttf"&gt;
            &lt;codepages&gt;
              &lt;codepage encoding="Cp1252"/&gt;
            &lt;/codepages&gt;
          &lt;/bolditalic&gt;
          &lt;italic embed="true" filename="ariali.ttf"&gt;
            &lt;codepages&gt;
              &lt;codepage encoding="Cp1252"/&gt;
            &lt;/codepages&gt;
          &lt;/italic&gt;
          &lt;bold embed="false" filename="arialbd.ttf"&gt;
            &lt;codepages&gt;
              &lt;codepage encoding="Cp1252"/&gt;
            &lt;/codepages&gt;
          &lt;/bold&gt;
          &lt;normal embed="true" filename="arial.ttf"&gt;
            &lt;codepages&gt;
              &lt;codepage encoding="Cp1252"/&gt;
            &lt;/codepages&gt;
          &lt;/normal&gt;
        &lt;/family&gt;
      &lt;/fonts&gt;
      &lt;description/&gt;
      &lt;PRESoptFile&gt;VGhlc2UgYXJlIG9ubHkgdGhlIG9wdGlvbnMgd2hpY2ggYXJlIGRpZmZlcmVudCBmcm9tIHRoZSBn
bG9iYWwgTVBQIG9wdGlvbnMuDUFGUERTX0Nscj0xMA1BRlBEU19FcHNDb250YWluZXI9ZmFsc2UN
QUZQRFNfRlM0NT10cnVlDUFGUERTX0pwZWdDb250YWluZXI9ZmFsc2UNQUZQRFNfTWF4VHJheU1h
cHBpbmc9MTANQUZQRFNfUGRmQ29udGFpbmVyPWZhbHNlDUFGUERTX1Jlc291cmNlRGlyPQ1BRlBE
U19SZXNvdXJjZU1hbmFnZW1lbnQ9MA1BRlBEU19UaWZmQ29udGFpbmVyPWZhbHNlDURTX0FsbG93
QXBwZW5kVG9PcGVuU3Bvb2w9ZmFsc2UNRFNfQWxsb3dVVEY4SW5wdXQ9dHJ1ZQ1EU19Gb250UGF0
aD0NRFNfR3JhcGhpY1BhdGg9DURTX1BESVBhdGg9DURTX1BSZVNDb21wYXRpYmlsaXR5TW9kZT1m
YWxzZQ1EU19QcmludFN0cmVhbUJ1ZmZlclNpemU9NjU1MzYNRFNfU3RhdHVzRmx1c2hPbldyaXRl
PWZhbHNlDURTX1N1cHByZXNzRXh0ZW5zaW9uPWZhbHNlDURTX1N5c3RlbVBhdGg9DURTX1RSRlBh
dGg9DUlKUERTX0NhdE9uZUZvbnRzPWZhbHNlDUlKUERTX0Nscl8wPTANSUpQRFNfQ29tcHJlc3Np
b249ZmFsc2UNSUpQRFNfQ3VyQ2ZnPVVubmFtZWQgQ29uZmlndXJhdGlvbg1JSlBEU19EcGx4U2lk
ZV8wPTANSUpQRFNfRHJhcGVfMD0wDUlKUERTX0Z1bGxDb2xvdXI9ZmFsc2UNSUpQRFNfTG9va1Vw
VGFibGU9DUlKUERTX051bURyb3BzXzBfMD0yDUlKUERTX051bUhlYWRzXzA9MQ1JSlBEU19OdW1K
ZXRzXzBfMD0yNjg4DUlKUERTX051bVJpcHM9MQ1JSlBEU19PZmZzZXRfMD0wDUlKUERTX1JlbEhl
YWRQb3NfMF8wPTANSUpQRFNfUmVxUmlwcz0xMjgNSUpQRFNfUmVzWF8wPTMwMA1JSlBEU19SZXNZ
XzA9MzAwDUlKUERTX1JpcE5hbWVfMD0NSUpQRFNfU09QQnJrUG9zPTANSVBEU19Db21wYXRpYmls
aXR5PWZhbHNlDUlQRFNfRk09MA1JUERTX0ZTMTE9ZmFsc2UNSVBEU19GUzQ1PWZhbHNlDUlQRFNf
SU09ZmFsc2UNSVBEU19JT0NvbXA9Mg1JUERTX09GPWZhbHNlDVBDTF9DbHI9OQ1QREZfTG9hZEFz
VmVjdG9yPXRydWUNUERGX09JQ29uZGl0aW9uPQ1QREZfT0lJQ0NQcm9maWxlRmlsZT0NUERGX09J
SW5mbz0NUERGX1N0YW5kYXJkPTANUERGX1ZlY3RvclBhZ2VUaHJlc2hvbGQ9MA1QTUdSX0lEQWRk
cmVzcz0xMjcuMC4wLjENUE1HUl9Qb3J0PTg1MTYNUE1HUl9RdWV1ZT1EZWZhdWx0DVBTQmluTWFw
cGluZ3NMaXN0PQ1QU1RyYXlNYXBwaW5nc0xpc3Q9DVJhc3Rlcl9BcHBlbmRUb0ZpbGU9ZmFsc2UN
UmFzdGVyX0pQR0F1dG9OdW09ZmFsc2UNUmFzdGVyX0pQR1N0YXJ0VmFsPTENUmFzdGVyX01vbm9j
aHJvbWU9ZmFsc2UNUmFzdGVyX091dHB1dD1USUZGDVZEWF9CaW5hcnk9dHJ1ZQ1WRFhfQ29tcHJl
c3M9dHJ1ZQ1WRFhfVHJheU1hcHBpbmdMaXN0PQ1WSVBQX0NvbnZlcnRUb1RpZmY9dHJ1ZQ0=&lt;/PRESoptFile&gt;
      &lt;colorMaps&gt;
        &lt;colorMap enabled="true" RGBHexCode="0x6A1DC" Cvalue="75" Mvalue="20" Yvalue="0" Kvalue="0"/&gt;
        &lt;colorMap enabled="true" RGBHexCode="0x9FC9EB" Cvalue="35" Mvalue="10" Yvalue="0" Kvalue="0"/&gt;
        &lt;colorMap enabled="true" RGBHexCode="0xD2EDF3" Cvalue="16" Mvalue="0" Yvalue="3" Kvalue="0"/&gt;
        &lt;colorMap enabled="true" RGBHexCode="0xEEF8F6" Cvalue="5" Mvalue="0" Yvalue="3" Kvalue="0"/&gt;
      &lt;/colorMaps&gt;
      &lt;PPDFile originalFileName="" imageCaching=""/&gt;
      &lt;PclSettings&gt;
        &lt;PclSetting enable="false" enableOffset="true" horizOffset="25400" vertOffset="50800" headerConstantCommand="" horizOffsetBack="25400" vertOffsetBack="50800" incrementWidth="false"/&gt;
      &lt;/PclSettings&gt;
      &lt;PdfSettings&gt;
        &lt;PdfSetting enable="false" profile="pdf" optimizeThinLines="false" thinLinesOptimizationThreshold="106" singleByteEncoding="false" deepPagesTree="false"/&gt;
      &lt;/PdfSettings&gt;
      &lt;AFPSettings useFormDef="true" forceMonoImages="false" forceBW="false" allowWhiteTextOnBW="false" useEBCDIC="false" G4compression="false" colorImagesFormat="jpeg"/&gt;
      &lt;ExcelSettings isXls="false" isXlsx="false"/&gt;
      &lt;EmailSettings body="1"/&gt;
      &lt;RasterSettings type="tiff" transparentBackground="true" highQuality="true" compression="rle"/&gt;
      &lt;EipaSettings eipaDocumentName=""&gt;
        &lt;attachment enable="false" includeAtt="false" sourceAtt=""&gt;
          &lt;internalAttachment enable="false" description=""/&gt;
          &lt;externalAttachment enable="false" description="" name="" format="" compression=""/&gt;
        &lt;/attachment&gt;
      &lt;/EipaSettings&gt;
      &lt;CsvSettings separator="semicolon"/&gt;
      &lt;IFSettings discardTransactionalData="false" storeImages="false"/&gt;
      &lt;ICSettings ttsCaching="true"/&gt;
    &lt;/target&gt;
  &lt;/targets&gt;
  &lt;serializers&gt;
    &lt;serializer name="DEFAULT" id="DEFAULT" codePage="Cp1252" countPersonalizedBlanksAsPers="false"&gt;
      &lt;description/&gt;
      &lt;customFields&gt;
        &lt;printjobFields&gt;
          &lt;field id="LOT_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;REVGQVVMVA==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="SEMAPHORE_BASE_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJJobId" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Xw==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRINT_FILE_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SSSpoolfilesCounter" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Lg==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJSpoolfileExtension" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRINT_SME_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LnNtZQ==&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_BASE_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="/FILE/DOCUMENT/@code" dataProvider="document"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Xw==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SSEnvelopesCounter" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_SPOOL_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="EMAIL_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Lg==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJSpoolfileExtension" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_LOTXML_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LmxvdHhtbA==&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_SEMAPHORE_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LnNtZQ==&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_BODY_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="EMAIL_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Lmh0bWw=&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_LOTXML_HEADER" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="5000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NPGxvdCB4bWxucz0iaHR0cDov
L2VkZWxpdmVyeS5lYmlsbGluZy5pdC9zY2hlbWEvbG90Ij4NPGV4dGVybmFsSWQ+MTwvZXh0ZXJu
YWxJZD4NPGRlc2NyaXB0aW9uPkJsdWVCYW5rIERlbW88L2Rlc2NyaXB0aW9uPg08cHJpb3JpdHk+
Tk9STUFMPC9wcmlvcml0eT4NPG1lc3NhZ2VzPg==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_LOTXML_FOOT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="1000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PC9tZXNzYWdlcz4NPHByb3BlcnRpZXM+DTxwcm9wZXJ0eSBuYW1lPSJMT1RfRVhURVJOQUxfSUQi
Pg08dmFsdWU+JExPVElEPC92YWx1ZT4NPC9wcm9wZXJ0eT4NPHByb3BlcnR5IG5hbWU9IklEX1BS
T0pFQ1QiPg08dmFsdWU+NTIyNDwvdmFsdWU+DTwvcHJvcGVydHk+DTxwcm9wZXJ0eSBuYW1lPSJM
T1RfUFJJT1JJVFkiPg08dmFsdWU+Tk9STUFMPC92YWx1ZT4NPC9wcm9wZXJ0eT4NPHByb3BlcnR5
IG5hbWU9IkxPVF9OT1RJRllfUkVDSVBJRU5UX1RPIj4NPHZhbHVlPiRMT1RfTk9USUZZX1JFQ0lQ
SUVOVF9UTzwvdmFsdWU+DTwvcHJvcGVydHk+DTxwcm9wZXJ0eSBuYW1lPSJMT1RfTk9USUZZX1JF
Q0lQSUVOVF9DQyI+DTx2YWx1ZT4kTE9UX05PVElGWV9SRUNJUElFTlRfQ0M8L3ZhbHVlPg08L3By
b3BlcnR5Pg08cHJvcGVydHkgbmFtZT0iTE9UX05PVElGWV9SRUNJUElFTlRfQkNDIj4NPHZhbHVl
PiRMT1RfTk9USUZZX1JFQ0lQSUVOVF9CQ0M8L3ZhbHVlPg08L3Byb3BlcnR5Pg08cHJvcGVydHkg
bmFtZT0iTE9UX05PVElGWV9GUk9NIj4NPHZhbHVlPiRMT1RfTk9USUZZX0ZST008L3ZhbHVlPg08
L3Byb3BlcnR5Pg08cHJvcGVydHkgbmFtZT0iTE9UX05PVElGWV9SRVBMWVRPIj4NPHZhbHVlPiRM
T1RfTk9USUZZX1JFUExZVE88L3ZhbHVlPg08L3Byb3BlcnR5Pg08cHJvcGVydHkgbmFtZT0iTE9U
X05PVElGWV9QUklPUklUWSI+DTx2YWx1ZT4kTE9UX05PVElGWV9QUklPUklUWTwvdmFsdWU+DTwv
cHJvcGVydHk+DTwvcHJvcGVydGllcz4NPGZyb21EYXRlPjIwMDAtMDEtMDE8L2Zyb21EYXRlPg08
ZXhwaXJ5RGF0ZT4yMDIwLTEyLTMxPC9leHBpcnlEYXRlPg08L2xvdD4=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_LOTXML_BODY" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="5000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PG1lc3NhZ2U+DTxnYXRld2F5cz4NPGdhdGV3YXk+DTxlbWFpbD4NPGNvZGVwYWdlPlVURi04PC9j
b2RlcGFnZT4NPHN1YmplY3Q+Qmx1ZUJhbmsgU3RhdGVtZW50ICMkSU5WT0lDRV9JRDwvc3ViamVj
dD4NPHJlY2lwaWVudHM+DTxyZWNpcGllbnQ+DTxhZGRyZXNzPiREU1RfRU1BSUw8L2FkZHJlc3M+
DTxuYW1lPiREU1RfTkFNRTwvbmFtZT4NPHR5cGU+VE88L3R5cGU+DTwvcmVjaXBpZW50Pg08L3Jl
Y2lwaWVudHM+DTxib2R5Pg08aHRtbD4NPHBhdGg+JEJPRFlfUEFUSDwvcGF0aD4NPC9odG1sPg08
L2JvZHk+DTxhdHRhY2htZW50cz4NPGh5cGVybGluaz4NPGZpbGU+DTxwbGFjZWhvbGRlcj5bc3Rh
dGVtZW50XTwvcGxhY2Vob2xkZXI+DTxwYXRoPiRBVFRBQ0hNRU5UX1BBVEg8L3BhdGg+DTwvZmls
ZT4NPC9oeXBlcmxpbms+DTwvYXR0YWNobWVudHM+DTxmcm9tPg08YWRkcmVzcz5ibHVlYmFua0Bk
b3hlZS5jb208L2FkZHJlc3M+DTxuYW1lPkRveGVlIEJsdWVCYW5rPC9uYW1lPg08L2Zyb20+DTxw
cmlvcml0eT5OT1JNQUw8L3ByaW9yaXR5Pg08ZGVsaXZlcnlTdGF0dXNOb3RpZmljYXRpb25zPmZh
bHNlPC9kZWxpdmVyeVN0YXR1c05vdGlmaWNhdGlvbnM+DTxtZXNzYWdlRGlzcG9zaXRpb25Ob3Rp
ZmljYXRpb25zPmZhbHNlPC9tZXNzYWdlRGlzcG9zaXRpb25Ob3RpZmljYXRpb25zPg08L2VtYWls
Pg08L2dhdGV3YXk+DTwvZ2F0ZXdheXM+DTwvbWVzc2FnZT4=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_LOTXML_BODY_RE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="5000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JElOVk9JQ0VfSUQ=&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PRX_INVOICE_ID" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JERTVF9FTUFJTA==&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PRX_DST_EMAIL" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JERTVF9OQU1F&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PRX_CUSTOMER_NAME" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JEJPRFlfUEFUSA==&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="EMAIL_BODY_NAME" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JEFUVEFDSE1FTlRfUEFUSA==&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="EMAIL_SPOOL_NAME" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="EMAIL_LOTXML_BODY" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRX_INVOICE_ID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/@code" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRX_CUSTOMER_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="210" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@fullName" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRX_DST_EMAIL" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="250" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@email" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_BODY_CONT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="12000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PGh0bWw+DTxoZWFkPg08dGl0bGU+Qmx1ZUJhbmsgU3RhdGVtZW50IGVtYWlsIG1lc3NhZ2U8L3Rp
dGxlPg08c3R5bGUgdHlwZT0idGV4dC9jc3MiPg1ib2R5IHsNbWFyZ2luOjA7DXBhZGRpbmc6MDsN
fQ0NI2xvZ29iYW5uZXIgew13aWR0aDoxMDAlOw19DQ0jbG9nbyB7DXBvc2l0aW9uOmFic29sdXRl
Ow1sZWZ0OjIwcHg7DW1hcmdpbi10b3A6M3B4Ow19DQ0jYmFubmVyIHsNd2lkdGg6MTAwJTsNaGVp
Z2h0OjU1cHg7DW1hcmdpbjowOw1iYWNrZ3JvdW5kOiAjMDZhMWRjOyAvKiBPbGQgYnJvd3NlcnMg
Ki8NYmFja2dyb3VuZDogLW1vei1saW5lYXItZ3JhZGllbnQobGVmdCwgICMwNmExZGMgMCUsICNl
ZWY4ZjYgMTAwJSk7IC8qIEZGMy42KyAqLw1iYWNrZ3JvdW5kOiAtd2Via2l0LWdyYWRpZW50KGxp
bmVhciwgbGVmdCB0b3AsIHJpZ2h0IHRvcCwgY29sb3Itc3RvcCgwJSwjMDZhMWRjKSwgY29sb3It
c3RvcCgxMDAlLCNlZWY4ZjYpKTsgLyogQ2hyb21lLFNhZmFyaTQrICovDWJhY2tncm91bmQ6IC13
ZWJraXQtbGluZWFyLWdyYWRpZW50KGxlZnQsICAjMDZhMWRjIDAlLCNlZWY4ZjYgMTAwJSk7IC8q
IENocm9tZTEwKyxTYWZhcmk1LjErICovDWJhY2tncm91bmQ6IC1vLWxpbmVhci1ncmFkaWVudChs
ZWZ0LCAgIzA2YTFkYyAwJSwjZWVmOGY2IDEwMCUpOyAvKiBPcGVyYSAxMS4xMCsgKi8NYmFja2dy
b3VuZDogLW1zLWxpbmVhci1ncmFkaWVudChsZWZ0LCAgIzA2YTFkYyAwJSwjZWVmOGY2IDEwMCUp
OyAvKiBJRTEwKyAqLw1iYWNrZ3JvdW5kOiBsaW5lYXItZ3JhZGllbnQobGVmdCwgICMwNmExZGMg
MCUsI2VlZjhmNiAxMDAlKTsgLyogVzNDICovDWZpbHRlcjogcHJvZ2lkOkRYSW1hZ2VUcmFuc2Zv
cm0uTWljcm9zb2Z0LmdyYWRpZW50KCBzdGFydENvbG9yc3RyPScjMDZhMWRjJywgZW5kQ29sb3Jz
dHI9JyNlZWY4ZjYnLEdyYWRpZW50VHlwZT0xICk7IC8qIElFNi05ICovDX0NDSNvdXRlckNvbnRl
bnQgew13aWR0aDo2MDBweDsNaGVpZ2h0OjE4MHB4Ow1tYXJnaW46YXV0bzsNbWFyZ2luLXRvcDox
MHB4Ow1mb250LWZhbWlseTogQXJpYWw7DWZvbnQtc2l6ZTogMTRweDsNfQ0NI2NvbnRlbnQgew13
aWR0aDo2MDBweDsNaGVpZ2h0OjE4MHB4Ow1ib3JkZXI6MXB4IHNvbGlkICMwNmExZGM7DXBhZGRp
bmc6MTBweDsNZm9udC1mYW1pbHk6SGVsdmV0aWNhLCBBcmlhbCwgc2Fucy1zZXJpZjsNY29sb3I6
IzA2YTFkYzsNfQ0NLnNpZ25hdHVyZSB7DWZvbnQtc3R5bGU6aXRhbGljOw1jb2xvcjpsaWdodGdy
ZXk7DXRleHQtYWxpZ246cmlnaHQ7DXdpZHRoOjEwMCU7DWZvbnQtc2l6ZToxMXB0Ow19DQ0jZGlz
Y2xhaW1lciB7DWZvbnQtc3R5bGU6aXRhbGljOw1jb2xvcjpsaWdodGdyZXk7DXRleHQtYWxpZ246
Y2VudGVyOw1mb250LXNpemU6OXB0Ow10b3A6MzAwcHg7DWZvbnQtZmFtaWx5OkhlbHZldGljYSwg
QXJpYWwsIHNhbnMtc2VyaWY7DQ0gICAgbWFyZ2luOiBhdXRvOw0gICAgcGFkZGluZy1sZWZ0OiA0
MHB4Ow0gICAgd2lkdGg6IDYyM3B4Ow0NfQ0NI2Zvb3RlciB7DXBvc2l0aW9uOiBhYnNvbHV0ZTsN
Ym90dG9tOiAwOw1sZWZ0OiAwOw13aWR0aDoxMDAlOw1oZWlnaHQ6MTBweDsNYmFja2dyb3VuZDog
IzA2YTFkYzsgLyogT2xkIGJyb3dzZXJzICovDWJhY2tncm91bmQ6IC1tb3otbGluZWFyLWdyYWRp
ZW50KGxlZnQsICAjMDZhMWRjIDAlLCAjZWVmOGY2IDEwMCUpOyAvKiBGRjMuNisgKi8NYmFja2dy
b3VuZDogLXdlYmtpdC1ncmFkaWVudChsaW5lYXIsIGxlZnQgdG9wLCByaWdodCB0b3AsIGNvbG9y
LXN0b3AoMCUsIzA2YTFkYyksIGNvbG9yLXN0b3AoMTAwJSwjZWVmOGY2KSk7IC8qIENocm9tZSxT
YWZhcmk0KyAqLw1iYWNrZ3JvdW5kOiAtd2Via2l0LWxpbmVhci1ncmFkaWVudChsZWZ0LCAgIzA2
YTFkYyAwJSwjZWVmOGY2IDEwMCUpOyAvKiBDaHJvbWUxMCssU2FmYXJpNS4xKyAqLw1iYWNrZ3Jv
dW5kOiAtby1saW5lYXItZ3JhZGllbnQobGVmdCwgICMwNmExZGMgMCUsI2VlZjhmNiAxMDAlKTsg
LyogT3BlcmEgMTEuMTArICovDWJhY2tncm91bmQ6IC1tcy1saW5lYXItZ3JhZGllbnQobGVmdCwg
ICMwNmExZGMgMCUsI2VlZjhmNiAxMDAlKTsgLyogSUUxMCsgKi8NYmFja2dyb3VuZDogbGluZWFy
LWdyYWRpZW50KGxlZnQsICAjMDZhMWRjIDAlLCNlZWY4ZjYgMTAwJSk7IC8qIFczQyAqLw1maWx0
ZXI6IHByb2dpZDpEWEltYWdlVHJhbnNmb3JtLk1pY3Jvc29mdC5ncmFkaWVudCggc3RhcnRDb2xv
cnN0cj0nIzA2YTFkYycsIGVuZENvbG9yc3RyPScjZWVmOGY2JyxHcmFkaWVudFR5cGU9MSApOyAv
KiBJRTYtOSAqLw19DQ0vKiBTaGFyZWQgc3R5bGVzICovDQ0gICAgICAgIC5kcm9wLXNoYWRvdyB7
DSAgICAgICAgICAgIHBvc2l0aW9uOnJlbGF0aXZlOw0gICAgICAgICAgICBmbG9hdDpsZWZ0Ow0g
ICAgICAgICAgICB3aWR0aDo0MCU7DSAgICAgICAgICAgIHBhZGRpbmc6MWVtOw0gICAgICAgICAg
ICBtYXJnaW46MmVtIDEwcHggMWVtOw0gICAgICAgICAgICBiYWNrZ3JvdW5kOiNmZmY7DSAgICAg
ICAgICAgIC13ZWJraXQtYm94LXNoYWRvdzowIDFweCA0cHggcmdiYSgwLCAwLCAwLCAwLjMpLCAw
IDAgNDBweCByZ2JhKDAsIDAsIDAsIDAuMSkgaW5zZXQ7DSAgICAgICAgICAgICAgIC1tb3otYm94
LXNoYWRvdzowIDFweCA0cHggcmdiYSgwLCAwLCAwLCAwLjMpLCAwIDAgNDBweCByZ2JhKDAsIDAs
IDAsIDAuMSkgaW5zZXQ7DSAgICAgICAgICAgICAgICAgICAgYm94LXNoYWRvdzowIDFweCA0cHgg
cmdiYSgwLCAwLCAwLCAwLjMpLCAwIDAgNDBweCByZ2JhKDAsIDAsIDAsIDAuMSkgaW5zZXQ7DSAg
ICAgICAgfQ0NICAgICAgICAuZHJvcC1zaGFkb3c6YmVmb3JlLA0gICAgICAgIC5kcm9wLXNoYWRv
dzphZnRlciB7DSAgICAgICAgICAgIGNvbnRlbnQ6IiI7DSAgICAgICAgICAgIHBvc2l0aW9uOmFi
c29sdXRlOw0gICAgICAgICAgICB6LWluZGV4Oi0yOw0gICAgICAgIH0NDS8qIExpZnRlZCBjb3Ju
ZXJzICovDQ0gICAgICAgIC5saWZ0ZWQgew0gICAgICAgICAgICAtbW96LWJvcmRlci1yYWRpdXM6
NHB4Ow0gICAgICAgICAgICAgICAgIGJvcmRlci1yYWRpdXM6NHB4Ow0gICAgICAgIH0NDSAgICAg
ICAgLmxpZnRlZDpiZWZvcmUsDSAgICAgICAgLmxpZnRlZDphZnRlciB7DSAgICAgICAgICAgIGJv
dHRvbToxNXB4Ow0gICAgICAgICAgICBsZWZ0OjEwcHg7DSAgICAgICAgICAgIHdpZHRoOjUwJTsN
ICAgICAgICAgICAgaGVpZ2h0OjIwJTsNICAgICAgICAgICAgbWF4LXdpZHRoOjMwMHB4Ow0gICAg
ICAgICAgICBtYXgtaGVpZ2h0OjEwMHB4Ow0gICAgICAgICAgICAtd2Via2l0LWJveC1zaGFkb3c6
MCAxNXB4IDEwcHggcmdiYSgwLCAwLCAwLCAwLjcpOw0gICAgICAgICAgICAgICAtbW96LWJveC1z
aGFkb3c6MCAxNXB4IDEwcHggcmdiYSgwLCAwLCAwLCAwLjcpOw0gICAgICAgICAgICAgICAgICAg
IGJveC1zaGFkb3c6MCAxNXB4IDEwcHggcmdiYSgwLCAwLCAwLCAwLjcpOw0gICAgICAgICAgICAt
d2Via2l0LXRyYW5zZm9ybTpyb3RhdGUoLTNkZWcpOw0gICAgICAgICAgICAgICAtbW96LXRyYW5z
Zm9ybTpyb3RhdGUoLTNkZWcpOw0gICAgICAgICAgICAgICAgLW1zLXRyYW5zZm9ybTpyb3RhdGUo
LTNkZWcpOw0gICAgICAgICAgICAgICAgIC1vLXRyYW5zZm9ybTpyb3RhdGUoLTNkZWcpOw0gICAg
ICAgICAgICAgICAgICAgIHRyYW5zZm9ybTpyb3RhdGUoLTNkZWcpOw0gICAgICAgIH0NDSAgICAg
ICAgLmxpZnRlZDphZnRlciB7DSAgICAgICAgICAgIHJpZ2h0OjEwcHg7DSAgICAgICAgICAgIGxl
ZnQ6YXV0bzsNICAgICAgICAgICAgLXdlYmtpdC10cmFuc2Zvcm06cm90YXRlKDNkZWcpOw0gICAg
ICAgICAgICAgICAtbW96LXRyYW5zZm9ybTpyb3RhdGUoM2RlZyk7DSAgICAgICAgICAgICAgICAt
bXMtdHJhbnNmb3JtOnJvdGF0ZSgzZGVnKTsNICAgICAgICAgICAgICAgICAtby10cmFuc2Zvcm06
cm90YXRlKDNkZWcpOw0gICAgICAgICAgICAgICAgICAgIHRyYW5zZm9ybTpyb3RhdGUoM2RlZyk7
DSAgICAgICAgfQ0NPC9zdHlsZT4NPC9oZWFkPg08Ym9keT4NPGRpdiBpZD0ibG9nb2Jhbm5lciI+
PC9kaXY+DTxkaXYgaWQ9ImxvZ28iPg08aW1nIHNyYz0iaHR0cDovL3VzMS5jbG91ZC5kb3hlZS5j
b20vaW1hZ2VzL2JsdWViYW5rL2xvZ28ucG5nIj4NPC9kaXY+DTxkaXYgaWQ9ImJhbm5lciI+PC9k
aXY+DTxkaXYgaWQ9Im91dGVyQ29udGVudCI+DTxkaXYgaWQ9ImNvbnRlbnQiIGNsYXNzPSJkcm9w
LXNoYWRvdyBsaWZ0ZWQiPg08cCBjbGFzcz0iY1RpdGxlIj4kTkFNRSw8L3A+DTxwPllvdXIgc2F0
ZXRlbWVudCBpcyBhdmFpbGFibGUgb25saW5lITwvcD4NPHA+PGEgaHJlZj0iW3N0YXRlbWVudF0i
PkNsaWNrIGhlcmU8L2E+IHRvIHZpZXcgdGhlIHN0YXRlbWVudCBvciB2aXNpdCA8YSBocmVmPSJ3
d3cuYmx1ZWJhbmsuY29tL29ubGluZSI+d3d3LmJsdWViYW5rLmNvbS9vbmxpbmU8L2E+IGFuZCBs
b2cgaW4gaW50byB5b3VyIHByaXZhdGUgYXJlYSBhbmQgdmlldyB0aGUgc3RhdGVtZW50IG9ubGlu
ZS48L3A+DTxwIGNsYXNzPSJzaWduYXR1cmUiPkJsdWVCYW5rPC9wPg08L2Rpdj4NPC9kaXY+DTxk
aXYgaWQ9ImRpc2NsYWltZXIiPg08cD5UaGlzIG1lc3NhZ2Ugd2FzIHNlbnQgdG8gJEVNQUlMIGJ5
IEJsdWVCYW5rPC9icj5CbHVlQmFuayB3aWxsIG5ldmVyIGFzayBmb3IgeW91c2VyIG5hbWUgYW5k
IHBhc3N3b3JkLiBJZiB5b3UgdGhpbmsgdGhpcyBtZXNzYWdlIGxvb2tzIHN1c3BpY2lvdXMsIHBs
ZWFzZSBjb250YWN0IDU1NSAxMjM0IDU2Nzg8L2JyPkJsdWVCYW5rLCAyMDMzIEdhdGV3YXkgUGxh
Y2UsIFN1aXRlIDUwMCwgOTUxMTAgU2FuIEpvc2UsIENBPC9wPg08L2Rpdj4NPGRpdiBpZD0iZm9v
dGVyIj48L2Rpdj4NPC9ib2R5Pg08L2h0bWw+&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_BODY_CONT_RE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="12000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JE5BTUU=&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PRX_CUSTOMER_NAME" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JEVNQUlM&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PRX_DST_EMAIL" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="EMAIL_BODY_CONT" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DATAMATRIX_VALUE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="72" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PRX_INVOICE_ID" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PRX_CUSTOMER_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PRX_STATE" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRX_STATE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressStateShort" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="IMB_VALUE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDEyMzQ1NjcwOTQ5ODc2NTQzMjEwMTIzNDU2Nzg5MQ==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550_FILENAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="256" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;const&gt;MDA1NTBfRUxPR0RBVEFfMDAwXw==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LnBhY2thZ2Vy&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560_FILENAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="256" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;const&gt;MDA1NjBfRUxPR0RBVEFfMDAwXw==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LnBhY2thZ2Vy&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_00_RECORDTYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDA=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_02_LOTID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_03_CLIENTID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="EXT_CLIENT_ID" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_04_ACCOUNTID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="EXT_ENV_ID" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_05_JOBID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_06_WORKTYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDE=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_07_WORKSTAGE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDA1NTA=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_08_OWNER" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="EXT_OWNER" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_09_HOSTNAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="20" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;RE9YRUU=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_10_APPTYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;REM=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_11_PROCEDURE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;Qmx1ZUJhbmsgU3RhdGVtZW50&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_12_PROCVERS" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="20" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MQ==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_13_JOBRESULT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="1" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MQ==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_14_AUTOCLOSE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="1" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MA==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_15_CUSTOM01" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_16_CUSTOM02" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_17_CUSTOM03" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_18_CUSTOM04" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550H_19_CUSTOM05" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_00_RECORDTYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDE=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_02_ID_ISTANZA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_03_ID_MISSIVA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="35" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJDocumentsCounter" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_04_ID_LOTTO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_05_NOME_LOTTO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="64" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_06_SIZE_LOTTO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_07_CODICE_P_P" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;QlBPX1VTUFM=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_08_ID_CONTAIN" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_09_NOME_CONTA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="64" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_10_TS_CREAZIO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="14" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTimestamp" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_11_ID_SOURCE_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJePublishCustomField2" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_12_FILENAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="SFFileName" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_13_FILEPATH" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="215" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="SFSpoolfilesAbsPath" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_14_FILE_SIZE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="18" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_15_FILE_TYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_16_ID_PROD" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJJobId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_17_TS_INIZIO_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="14" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTimestamp" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_18_TS_FINE_JO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="14" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTimestamp" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_19_RECORD_STA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DODatafileStartPos" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_20_RECORD_END" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DODatafileStartPos" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_21_PROGRESSIV" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJDocumentsCounter" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_22_PROGRESSIV" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJPersonCoverExtraPagesCounter" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_23_DOCUMENTI" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTotalTemplates" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_24_PAGINE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTotalPersCoverPages" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_25_PAGINE_BIA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTotalFillPages" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_26_FOGLI" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="DOTotalPersCoverExtraSheets" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_27_BOLLETTINI" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MA==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_28_VIA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressLine1" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_29_CAP" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressZipCode" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_30_LOCALITA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="30" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressCity" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_31_PROVINCIA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressStateLong" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_32_ANAGRAFICA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_33_ANAGRAFICA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_34_ANAGRAFICA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_35_CODICE_DOC" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJDocumentsCounter" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_36_TIPO_DOCUM" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_37_CANALE_P" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDE=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_38_FORMATO_P" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDE=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_39_EMISSIONE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJJobId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_40_SOCIETA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="20" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_41_DIVISIONE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="20" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_42_MERCATO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="64" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_43_IMPORTO_TO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="21" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_44_CODICE_MOD" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_45_CODICE_COL" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_46_CODICE_DUP" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_47_NUMRACCAND" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="11" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_48_NUMRACCRIT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="11" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_49_BARCODE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="20" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_50_AREA_POSTA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;ZGVmYXVsdA==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_51_PESO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="ENV_TOTAL_WEIGHT" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_52_ALLEGATI_T" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_53_NUM_ALLEGA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="18" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_54_ALLEGATI_T" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_55_NUM_ALLEGA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="18" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_56_ALLEGATI_T" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_57_NUM_ALLEGA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="18" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_58_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_59_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_60_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_61_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_62_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_63_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_64_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_65_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="15" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_66_ID_SUB_PRO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_67_CUSTOM_VC_" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560H_01_ID_JOB" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJJobId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560H_02_ID_LOTTO" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_01_ID_BUSTA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="35" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_02_ID_DOCUMEN" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="35" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_03_CODICE_MOD" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDY=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_04_TIPOLOGIA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_05_ID_ACQUISI" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="15" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_06_DATA_SCADE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="19" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_07_DATA_EMISS" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="19" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MjAxMjA3MjAyMDIwMjA=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_08_CODICE_DOC" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_09_CODICE_DES" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="32" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@customerCode" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_10_NOME_DESTI" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_11_PIVACF_DES" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="16" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_12_IMPORTO_PA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="21" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_13_PESO_DOCUM" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="22" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="ENV_SHEETS_WEIGHT" dataProvider="custom"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_14_PRESENZA_B" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="1" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MA==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_15_CODICE_DOC" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="128" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EXT_ID_CAPTURE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJePublishCustomField2" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EXT_CLIENT_ID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJePublishCustomField3" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EXT_ENV_ID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJePublishCustomField4" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EXT_CHANNEL_ID" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJePublishCustomField1" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EXT_OWNER" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="PJePublishCustomField5" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_07_CODICE_P_E" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;RUJJX0VCSQ==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_37_CANALE_E" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDQ=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_38_FORMATO_E" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDI=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_07_CODICE_P_A" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;RUJJX0VCSQ==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_37_CANALE_A" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDI=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR550D_38_FORMATO_A" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="8" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDI=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560D_00_RECORDTYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="left" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDE=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="TR560H_00_RECORDTYPE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="2" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;MDA=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ENV_TOTAL_WEIGHT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;number approx="none"/&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;math&gt;
                    &lt;add/&gt;
                  &lt;/math&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="ENV_SHEETS_WEIGHT" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;NQ==&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ENV_SHEETS_WEIGHT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;number approx="none"/&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;math&gt;
                    &lt;multiply/&gt;
                  &lt;/math&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;const&gt;NQ==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="DOTotalPersCoverExtraSheets" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ARCH_SPOOL_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="ARCH_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Lg==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PJSpoolfileExtension" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ARCH_BASE_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="/FILE/DOCUMENT/@code" dataProvider="document"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;Xw==&lt;/const&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SSEnvelopesCounter" dataProvider="system"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="EMAIL_LOTXML_FOOT_RE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="1000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JExPVElE&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="EMAIL_LOTXML_FOOT" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DOCLIST_HEADER" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PGRvY2xpc3Q+PGNyZWF0ZWQ+JHtDUkVBVEVEfTwvY3JlYXRlZD4=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DOCLIST_DOCUMENT" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="300" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PGRvYyBucHJvZz0iMDAwMDAxIiBrMT0iIiBrMj0iIiBrMz0iIiBrND0iIiBrNT0iIiBrNj0iIiBr
Nz0iIiBrOD0iIiBrOT0iIiBrMTA9IiIgazExPSIiIGsxMj0iIiBrMTM9IiIgazE0PSIiIGsxNT0i
IiBrMTY9IiIgazE3PSIiIGsxOD0iIiBrMTk9IiIgazIwPSIiIHBkZj0iJHtOQU1FfSIgLz4=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DOCLIST_FOOTER" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="20" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PC9kb2NsaXN0Pg==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DOCLIST_FILE_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="50" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;ZXByb29mX2RvY2xpc3QueG1s&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DOCLIST_DOCUMENT_REP" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="300" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JHtOQU1FfQ==&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="ARCH_SPOOL_NAME" dataProvider="custom"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="DOCLIST_DOCUMENT" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="DOCLIST_HEADER_REP" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JHtDUkVBVEVEfQ==&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PJStartTimestamp" dataProvider="system"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="DOCLIST_HEADER" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PROGRESSIVO_BUSTA" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="SFEnvelopesCounter" dataProvider="system"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRINT_LOTXML_BODY" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="5000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NPGxvdCB4bWxucz0iaHR0cDov
L2VkZWxpdmVyeS5lYmlsbGluZy5pdC9zY2hlbWEvbG90IiB4bWxuczp4c2k9Imh0dHA6Ly93d3cu
dzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIj4NPGV4dGVybmFsSWQ+JExPVElEPC9leHRl
cm5hbElkPg08ZGVzY3JpcHRpb24+Qmx1ZUJhbmsgRlRQIDwvZGVzY3JpcHRpb24+DTxwcmlvcml0
eT5ISUdIPC9wcmlvcml0eT4NPG1lc3NhZ2VzPg08bWVzc2FnZT4NPGdhdGV3YXlzPg08Z2F0ZXdh
eT4NPGZ0cD4NPGZpbGVzPg08ZmlsZT4NPHBhdGg+cHJpbnQuemlwPC9wYXRoPg08L2ZpbGU+DTwv
ZmlsZXM+DTwvZnRwPg08L2dhdGV3YXk+DTwvZ2F0ZXdheXM+DTwvbWVzc2FnZT4NPC9tZXNzYWdl
cz4NPC9sb3Q+&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRINT_LOTXML_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LmxvdHhtbA==&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PRINT_LOTXML_BODY_RE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="1000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JExPVElE&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="PRINT_LOTXML_BODY" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ARCH_LOTXML_BODY" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="5000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NPGxvdCB4bWxucz0iaHR0cDov
L2VkZWxpdmVyeS5lYmlsbGluZy5pdC9zY2hlbWEvbG90IiB4bWxuczp4c2k9Imh0dHA6Ly93d3cu
dzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIj4NPGV4dGVybmFsSWQ+JExPVElEPC9leHRl
cm5hbElkPg08ZGVzY3JpcHRpb24+Qmx1ZUJhbmsgRlRQIDwvZGVzY3JpcHRpb24+DTxwcmlvcml0
eT5ISUdIPC9wcmlvcml0eT4NPG1lc3NhZ2VzPg08bWVzc2FnZT4NPGdhdGV3YXlzPg08Z2F0ZXdh
eT4NPGZ0cD4NPGZpbGVzPg08ZmlsZT4NPHBhdGg+YXJjaGl2ZS56aXA8L3BhdGg+DTwvZmlsZT4N
PC9maWxlcz4NPC9mdHA+DTwvZ2F0ZXdheT4NPC9nYXRld2F5cz4NPC9tZXNzYWdlPg08L21lc3Nh
Z2VzPg08L2xvdD4=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ARCH_LOTXML_BODY_RE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="1000" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;replace&gt;
                      &lt;replacementToken&gt;
                        &lt;source&gt;
                          &lt;const&gt;JExPVElE&lt;/const&gt;
                        &lt;/source&gt;
                        &lt;replacement&gt;
                          &lt;value fieldRef="PJLotId" dataProvider="system"/&gt;
                        &lt;/replacement&gt;
                      &lt;/replacementToken&gt;
                    &lt;/replace&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="ARCH_LOTXML_BODY" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="ARCH_LOTXML_NAME" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="100" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                  &lt;operand&gt;
                    &lt;const&gt;LmxvdHhtbA==&lt;/const&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="OWNER_PW" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;b3duZXI=&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="USER_PW" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;const&gt;dXNlcg==&lt;/const&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PWD_USER_DATAFILE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="USER_1" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="PWD_OWNER_DATAFILE" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;expression&gt;
                &lt;operator&gt;
                  &lt;text&gt;
                    &lt;concatenate&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                    &lt;/concatenate&gt;
                  &lt;/text&gt;
                &lt;/operator&gt;
                &lt;operands&gt;
                  &lt;operand&gt;
                    &lt;value fieldRef="OWNER_1" dataProvider="custom"/&gt;
                  &lt;/operand&gt;
                &lt;/operands&gt;
              &lt;/expression&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="OWNER_1" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@lastName" dataProvider="document"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
          &lt;field id="USER_1" dataProvider="custom"&gt;
            &lt;type&gt;
              &lt;string align="none" length="10" case="none"&gt;
                &lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;
              &lt;/string&gt;
            &lt;/type&gt;
            &lt;assign&gt;
              &lt;reference fieldRef="/FILE/DOCUMENT/TEMPLATE/ACCOUNT/@accountNumber" dataProvider="template"/&gt;
            &lt;/assign&gt;
            &lt;description/&gt;
          &lt;/field&gt;
        &lt;/printjobFields&gt;
        &lt;documentFields/&gt;
        &lt;envelopeFields/&gt;
        &lt;lotFields/&gt;
        &lt;spoolsetFields/&gt;
        &lt;spoolfileFields/&gt;
        &lt;templateFields/&gt;
        &lt;pageFields/&gt;
      &lt;/customFields&gt;
      &lt;systemFields&gt;
        &lt;printjobFields&gt;
          &lt;systemField id="PJIndexRecsCountLOTXML_PRINT" defId="PJIndexRecsCount" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="PJIndexRecsCountTRACKING550P" defId="PJIndexRecsCount" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="PJIndexFileNameTRACKING550P" defId="PJIndexFileName" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="PJIndexFileNameTRACKING550E" defId="PJIndexFileName" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="PJIndexFileNameTRACKING550A" defId="PJIndexFileName" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="PJIndexFileNameTRACKING560A" defId="PJIndexFileName" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="PJIndexFullFileNameSME_FILE" defId="PJIndexFullFileName" instanceId="SME_FILE"/&gt;
          &lt;systemField id="PJIndexFullFileNameSME_FILE_EMAIL" defId="PJIndexFullFileName" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="PJIndexRecsCountTRACKING550A" defId="PJIndexRecsCount" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="PJIndexFullFileNameLOTXML" defId="PJIndexFullFileName" instanceId="LOTXML"/&gt;
          &lt;systemField id="PJIndexFullFileNameTRACKING560E" defId="PJIndexFullFileName" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="PJIndexFullFileNameTRACKING550P" defId="PJIndexFullFileName" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="PJIndexRecsCountTRACKING560A" defId="PJIndexRecsCount" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="PJIndexRecsCountDOCLIST" defId="PJIndexRecsCount" instanceId="DOCLIST"/&gt;
          &lt;systemField id="PJIndexRecsCountLOTXML_ARCHIVE" defId="PJIndexRecsCount" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="PJIndexFullFileNameTRACKING550E" defId="PJIndexFullFileName" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="PJIndexRecsCountLOTXML" defId="PJIndexRecsCount" instanceId="LOTXML"/&gt;
          &lt;systemField id="PJIndexFullFileNameLOTXML_ARCHIVE" defId="PJIndexFullFileName" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="PJIndexFullFileNameDOCLIST" defId="PJIndexFullFileName" instanceId="DOCLIST"/&gt;
          &lt;systemField id="PJIndexFullFileNameTRACKING560A" defId="PJIndexFullFileName" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="PJIndexRecsCountTRACKING550E" defId="PJIndexRecsCount" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="PJIndexFileNameLOTXML_PRINT" defId="PJIndexFileName" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="PJIndexRecsCountTRACKING560P" defId="PJIndexRecsCount" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="PJIndexFileNameSME_FILE" defId="PJIndexFileName" instanceId="SME_FILE"/&gt;
          &lt;systemField id="PJIndexRecsCountSME_FILE" defId="PJIndexRecsCount" instanceId="SME_FILE"/&gt;
          &lt;systemField id="PJIndexFileNameSME_FILE_EMAIL" defId="PJIndexFileName" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="PJIndexFullFileNameEMAIL_BODY" defId="PJIndexFullFileName" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="PJIndexFullFileNameTRACKING550A" defId="PJIndexFullFileName" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="PJIndexFullFileNameLOTXML_PRINT" defId="PJIndexFullFileName" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="PJIndexFileNameDOCLIST" defId="PJIndexFileName" instanceId="DOCLIST"/&gt;
          &lt;systemField id="PJIndexFullFileNameTRACKING560P" defId="PJIndexFullFileName" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="PJIndexRecsCountEMAIL_BODY" defId="PJIndexRecsCount" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="PJIndexFileNameEMAIL_BODY" defId="PJIndexFileName" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="PJIndexFileNameLOTXML" defId="PJIndexFileName" instanceId="LOTXML"/&gt;
          &lt;systemField id="PJIndexRecsCountTRACKING560E" defId="PJIndexRecsCount" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="PJIndexFileNameTRACKING560P" defId="PJIndexFileName" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="PJIndexFileNameLOTXML_ARCHIVE" defId="PJIndexFileName" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="PJIndexFileNameTRACKING560E" defId="PJIndexFileName" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="PJIndexRecsCountSME_FILE_EMAIL" defId="PJIndexRecsCount" instanceId="SME_FILE_EMAIL"/&gt;
        &lt;/printjobFields&gt;
        &lt;documentFields/&gt;
        &lt;envelopeFields/&gt;
        &lt;lotFields&gt;
          &lt;systemField id="LotNameDEFAULT" defId="LotName" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnveloper4BitsSeqNumberDEFAULT" defId="LotEnveloper4BitsSeqNumber" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotExtraPagesCounterDEFAULT" defId="LotExtraPagesCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPersCoverExtraSheetsCounterDEFAULT" defId="LotPersCoverExtraSheetsCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotFillSheetsCounterDEFAULT" defId="LotFillSheetsCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotExtraSheetsCounterDEFAULT" defId="LotExtraSheetsCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnveloper4BitsGroupNumberDEFAULT" defId="LotEnveloper4BitsGroupNumber" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotSheetsCounter_PAGETAG2DEFAULT" defId="LotSheetsCounter_PAGETAG2" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPagesCounter_PAGETAG1DEFAULT" defId="LotPagesCounter_PAGETAG1" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotSheetsCounter_PAGETAG3DEFAULT" defId="LotSheetsCounter_PAGETAG3" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotSheetsCounter_PAGETAG1DEFAULT" defId="LotSheetsCounter_PAGETAG1" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPagesCounter_PAGETAG3DEFAULT" defId="LotPagesCounter_PAGETAG3" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotFillPagesCounterDEFAULT" defId="LotFillPagesCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnveloper3BitsGroupNumberDEFAULT" defId="LotEnveloper3BitsGroupNumber" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotCoverSheetsCounterDEFAULT" defId="LotCoverSheetsCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPagesCounter_PAGETAG4DEFAULT" defId="LotPagesCounter_PAGETAG4" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPersCoverExtraPagesCounterDEFAULT" defId="LotPersCoverExtraPagesCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotCoverPagesCounterDEFAULT" defId="LotCoverPagesCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotSheetsCounter_PAGETAG4DEFAULT" defId="LotSheetsCounter_PAGETAG4" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPersCoverPagesCounterDEFAULT" defId="LotPersCoverPagesCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotIdDEFAULT" defId="LotId" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnvelopesCounterDEFAULT" defId="LotEnvelopesCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnveloper5BitsGroupNumberDEFAULT" defId="LotEnveloper5BitsGroupNumber" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnveloper5BitsSeqNumberDEFAULT" defId="LotEnveloper5BitsSeqNumber" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPagesCounter_PAGETAG2DEFAULT" defId="LotPagesCounter_PAGETAG2" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotEnveloper3BitsSeqNumberDEFAULT" defId="LotEnveloper3BitsSeqNumber" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPersonalizedSheetsCounterDEFAULT" defId="LotPersonalizedSheetsCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPersCoverSheetsCounterDEFAULT" defId="LotPersCoverSheetsCounter" instanceId="DEFAULT"/&gt;
          &lt;systemField id="LotPersonalizedPagesCounterDEFAULT" defId="LotPersonalizedPagesCounter" instanceId="DEFAULT"/&gt;
        &lt;/lotFields&gt;
        &lt;spoolsetFields&gt;
          &lt;systemField id="SSIndexFileNameTRACKING550P" defId="SSIndexFileName" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="SSIndexFileNameEMAIL_BODY" defId="SSIndexFileName" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="SSIndexFullFileNameSME_FILE_EMAIL" defId="SSIndexFullFileName" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="SSIndexRecsCountTRACKING560P" defId="SSIndexRecsCount" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="SSIndexFullFileNameLOTXML_PRINT" defId="SSIndexFullFileName" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="SSIndexRecsCountDOCLIST" defId="SSIndexRecsCount" instanceId="DOCLIST"/&gt;
          &lt;systemField id="SSIndexFullFileNameTRACKING560P" defId="SSIndexFullFileName" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="SSIndexRecsCountEMAIL_BODY" defId="SSIndexRecsCount" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="SSIndexRecsCountSME_FILE" defId="SSIndexRecsCount" instanceId="SME_FILE"/&gt;
          &lt;systemField id="SSIndexRecsCountTRACKING560A" defId="SSIndexRecsCount" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="SSIndexFileNameTRACKING550E" defId="SSIndexFileName" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="SSIndexFileNameTRACKING560E" defId="SSIndexFileName" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="SSIndexFileNameLOTXML" defId="SSIndexFileName" instanceId="LOTXML"/&gt;
          &lt;systemField id="SSIndexFullFileNameLOTXML_ARCHIVE" defId="SSIndexFullFileName" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="SSIndexRecsCountTRACKING550A" defId="SSIndexRecsCount" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="SSIndexFileNameTRACKING560A" defId="SSIndexFileName" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="SSIndexFileNameLOTXML_PRINT" defId="SSIndexFileName" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="SSIndexFileNameSME_FILE" defId="SSIndexFileName" instanceId="SME_FILE"/&gt;
          &lt;systemField id="SSIndexRecsCountTRACKING550P" defId="SSIndexRecsCount" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="SSIndexFileNameLOTXML_ARCHIVE" defId="SSIndexFileName" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="SSIndexFileNameTRACKING550A" defId="SSIndexFileName" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="SSIndexFileNameTRACKING560P" defId="SSIndexFileName" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="SSIndexFullFileNameEMAIL_BODY" defId="SSIndexFullFileName" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="SSIndexFullFileNameTRACKING550P" defId="SSIndexFullFileName" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="SSIndexFullFileNameTRACKING550E" defId="SSIndexFullFileName" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="SSIndexRecsCountLOTXML" defId="SSIndexRecsCount" instanceId="LOTXML"/&gt;
          &lt;systemField id="SSIndexFileNameSME_FILE_EMAIL" defId="SSIndexFileName" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="SSIndexRecsCountLOTXML_ARCHIVE" defId="SSIndexRecsCount" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="SSIndexFullFileNameSME_FILE" defId="SSIndexFullFileName" instanceId="SME_FILE"/&gt;
          &lt;systemField id="SSIndexRecsCountTRACKING550E" defId="SSIndexRecsCount" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="SSIndexFullFileNameLOTXML" defId="SSIndexFullFileName" instanceId="LOTXML"/&gt;
          &lt;systemField id="SSIndexFullFileNameTRACKING560A" defId="SSIndexFullFileName" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="SSIndexRecsCountTRACKING560E" defId="SSIndexRecsCount" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="SSIndexRecsCountSME_FILE_EMAIL" defId="SSIndexRecsCount" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="SSIndexFullFileNameTRACKING550A" defId="SSIndexFullFileName" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="SSIndexFullFileNameTRACKING560E" defId="SSIndexFullFileName" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="SSIndexFileNameDOCLIST" defId="SSIndexFileName" instanceId="DOCLIST"/&gt;
          &lt;systemField id="SSIndexRecsCountLOTXML_PRINT" defId="SSIndexRecsCount" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="SSIndexFullFileNameDOCLIST" defId="SSIndexFullFileName" instanceId="DOCLIST"/&gt;
        &lt;/spoolsetFields&gt;
        &lt;spoolfileFields&gt;
          &lt;systemField id="SFIndexFileNameTRACKING550E" defId="SFIndexFileName" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="SFIndexFullFileNameTRACKING550E" defId="SFIndexFullFileName" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="SFIndexFullFileNameTRACKING550P" defId="SFIndexFullFileName" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="SFIndexFileNameLOTXML_PRINT" defId="SFIndexFileName" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="SFIndexFileNameSME_FILE_EMAIL" defId="SFIndexFileName" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="SFIndexFullFileNameLOTXML" defId="SFIndexFullFileName" instanceId="LOTXML"/&gt;
          &lt;systemField id="SFIndexFileNameTRACKING560P" defId="SFIndexFileName" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="SFIndexRecsCountTRACKING550P" defId="SFIndexRecsCount" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="SFIndexRecsCountSME_FILE_EMAIL" defId="SFIndexRecsCount" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="SFIndexFullFileNameSME_FILE_EMAIL" defId="SFIndexFullFileName" instanceId="SME_FILE_EMAIL"/&gt;
          &lt;systemField id="SFIndexFileNameTRACKING550A" defId="SFIndexFileName" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="SFIndexFileNameEMAIL_BODY" defId="SFIndexFileName" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="SFIndexFullFileNameSME_FILE" defId="SFIndexFullFileName" instanceId="SME_FILE"/&gt;
          &lt;systemField id="SFIndexFullFileNameLOTXML_ARCHIVE" defId="SFIndexFullFileName" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="SFIndexFullFileNameTRACKING560A" defId="SFIndexFullFileName" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="SFIndexFileNameSME_FILE" defId="SFIndexFileName" instanceId="SME_FILE"/&gt;
          &lt;systemField id="SFIndexFileNameDOCLIST" defId="SFIndexFileName" instanceId="DOCLIST"/&gt;
          &lt;systemField id="SFIndexRecsCountLOTXML" defId="SFIndexRecsCount" instanceId="LOTXML"/&gt;
          &lt;systemField id="SFIndexRecsCountSME_FILE" defId="SFIndexRecsCount" instanceId="SME_FILE"/&gt;
          &lt;systemField id="SFIndexRecsCountEMAIL_BODY" defId="SFIndexRecsCount" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="SFIndexRecsCountTRACKING560E" defId="SFIndexRecsCount" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="SFIndexRecsCountTRACKING560P" defId="SFIndexRecsCount" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="SFIndexFullFileNameDOCLIST" defId="SFIndexFullFileName" instanceId="DOCLIST"/&gt;
          &lt;systemField id="SFIndexFullFileNameTRACKING560P" defId="SFIndexFullFileName" instanceId="TRACKING560P"/&gt;
          &lt;systemField id="SFIndexFullFileNameTRACKING560E" defId="SFIndexFullFileName" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="SFIndexRecsCountTRACKING550E" defId="SFIndexRecsCount" instanceId="TRACKING550E"/&gt;
          &lt;systemField id="SFIndexFileNameTRACKING550P" defId="SFIndexFileName" instanceId="TRACKING550P"/&gt;
          &lt;systemField id="SFIndexRecsCountLOTXML_ARCHIVE" defId="SFIndexRecsCount" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="SFIndexFullFileNameLOTXML_PRINT" defId="SFIndexFullFileName" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="SFIndexRecsCountLOTXML_PRINT" defId="SFIndexRecsCount" instanceId="LOTXML_PRINT"/&gt;
          &lt;systemField id="SFIndexFileNameTRACKING560A" defId="SFIndexFileName" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="SFIndexFullFileNameTRACKING550A" defId="SFIndexFullFileName" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="SFIndexRecsCountDOCLIST" defId="SFIndexRecsCount" instanceId="DOCLIST"/&gt;
          &lt;systemField id="SFIndexRecsCountTRACKING560A" defId="SFIndexRecsCount" instanceId="TRACKING560A"/&gt;
          &lt;systemField id="SFIndexFileNameTRACKING560E" defId="SFIndexFileName" instanceId="TRACKING560E"/&gt;
          &lt;systemField id="SFIndexFullFileNameEMAIL_BODY" defId="SFIndexFullFileName" instanceId="EMAIL_BODY"/&gt;
          &lt;systemField id="SFIndexRecsCountTRACKING550A" defId="SFIndexRecsCount" instanceId="TRACKING550A"/&gt;
          &lt;systemField id="SFIndexFileNameLOTXML_ARCHIVE" defId="SFIndexFileName" instanceId="LOTXML_ARCHIVE"/&gt;
          &lt;systemField id="SFIndexFileNameLOTXML" defId="SFIndexFileName" instanceId="LOTXML"/&gt;
        &lt;/spoolfileFields&gt;
        &lt;templateFields/&gt;
        &lt;pageFields/&gt;
      &lt;/systemFields&gt;
      &lt;lots&gt;
        &lt;lot id="DEFAULT" name="DEFAULT"/&gt;
      &lt;/lots&gt;
      &lt;envelopeManagement&gt;
        &lt;envelopeCreation&gt;
          &lt;envelopeCapacity fieldRef="PJConstantZero" dataProvider="system"/&gt;
          &lt;multienvelope fieldRef="PJConstantFalse" dataProvider="system"/&gt;
          &lt;useCover fieldRef="PJConstantFalse" dataProvider="system"/&gt;
          &lt;coverOnFirstEnvelope fieldRef="PJConstantFalse" dataProvider="system"/&gt;
          &lt;envelopeExtraSheets&gt;
            &lt;firstEnvelope fieldRef="PJConstantZero" dataProvider="system"/&gt;
            &lt;allEnvelopes fieldRef="PJConstantZero" dataProvider="system"/&gt;
          &lt;/envelopeExtraSheets&gt;
        &lt;/envelopeCreation&gt;
        &lt;envelopeDispatching&gt;
          &lt;destinationLot fieldRef="LOT_NAME" dataProvider="custom"/&gt;
        &lt;/envelopeDispatching&gt;
        &lt;envelopeInserts enabled="false"&gt;
          &lt;Insert1&gt;
            &lt;label/&gt;
            &lt;enableOnFirstEnvelope/&gt;
            &lt;enableOnAllEnvelopes/&gt;
            &lt;sheetsCount/&gt;
          &lt;/Insert1&gt;
          &lt;Insert2&gt;
            &lt;label/&gt;
            &lt;enableOnFirstEnvelope/&gt;
            &lt;enableOnAllEnvelopes/&gt;
            &lt;sheetsCount/&gt;
          &lt;/Insert2&gt;
          &lt;Insert3&gt;
            &lt;label/&gt;
            &lt;enableOnFirstEnvelope/&gt;
            &lt;enableOnAllEnvelopes/&gt;
            &lt;sheetsCount/&gt;
          &lt;/Insert3&gt;
          &lt;Insert4&gt;
            &lt;label/&gt;
            &lt;enableOnFirstEnvelope/&gt;
            &lt;enableOnAllEnvelopes/&gt;
            &lt;sheetsCount/&gt;
          &lt;/Insert4&gt;
        &lt;/envelopeInserts&gt;
      &lt;/envelopeManagement&gt;
      &lt;trayManagement enabled="false" defaultTray="1" modality="static"/&gt;
      &lt;fileManagement&gt;
        &lt;fileManagementConfiguration id="PRINT" name="PRINT" errorManagement="stop" spoolingOnError="true" reduceWorkingSpace="true"&gt;
          &lt;printjob&gt;
            &lt;index name="TRACKING550" id="TRACKING550P" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="TR550_FILENAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_02_LOTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_03_CLIENTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_04_ACCOUNTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_05_JOBID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_06_WORKTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_07_WORKSTAGE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_08_OWNER" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_09_HOSTNAME" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_10_APPTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_11_PROCEDURE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_12_PROCVERS" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_13_JOBRESULT" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_14_AUTOCLOSE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_15_CUSTOM01" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_16_CUSTOM02" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_17_CUSTOM03" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_18_CUSTOM04" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_19_CUSTOM05" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_02_ID_ISTANZA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_04_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_05_NOME_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_06_SIZE_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_07_CODICE_P_P" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_08_ID_CONTAIN" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_09_NOME_CONTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_10_TS_CREAZIO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_12_FILENAME" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_13_FILEPATH" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_14_FILE_SIZE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_15_FILE_TYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_16_ID_PROD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_17_TS_INIZIO_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_18_TS_FINE_JO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_19_RECORD_STA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_20_RECORD_END" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_21_PROGRESSIV" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_22_PROGRESSIV" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_23_DOCUMENTI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_24_PAGINE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_25_PAGINE_BIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_26_FOGLI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_27_BOLLETTINI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_28_VIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_29_CAP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_30_LOCALITA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_31_PROVINCIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_32_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_33_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_34_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_35_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_36_TIPO_DOCUM" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_37_CANALE_P" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_38_FORMATO_P" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_39_EMISSIONE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_40_SOCIETA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_41_DIVISIONE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_42_MERCATO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_43_IMPORTO_TO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_44_CODICE_MOD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_45_CODICE_COL" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_46_CODICE_DUP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_47_NUMRACCAND" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_48_NUMRACCRIT" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_49_BARCODE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_50_AREA_POSTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_51_PESO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_52_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_53_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_54_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_55_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_56_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_57_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_58_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_59_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_60_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_61_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_62_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_63_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_64_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_65_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_66_ID_SUB_PRO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_67_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;index name="TRACKING560" id="TRACKING560P" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="TR560_FILENAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_01_ID_BUSTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_02_ID_DOCUMEN" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_03_CODICE_MOD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_04_TIPOLOGIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_05_ID_ACQUISI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_06_DATA_SCADE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_07_DATA_EMISS" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_08_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_09_CODICE_DES" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_10_NOME_DESTI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_11_PIVACF_DES" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_12_IMPORTO_PA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_13_PESO_DOCUM" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_14_PRESENZA_B" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_15_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;dataTracing enabled="false" respectBreakRules="false"&gt;
              &lt;dataTraceFile/&gt;
            &lt;/dataTracing&gt;
          &lt;/printjob&gt;
          &lt;spoolsets multiple="false"&gt;
            &lt;spoolset splitResolution="template" id="DEFAULT" suppressBackPages="false" trailingSheet="false" leadingSheet="false"&gt;
              &lt;index name="SME_FILE" id="SME_FILE" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
                &lt;fileName fieldRef="PRINT_SME_NAME" dataProvider="custom"/&gt;
                &lt;spoolsetEnd&gt;
                  &lt;record terminator="crlf" name="SME Content" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;value fieldRef="PRINT_SME_NAME" dataProvider="custom"/&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/spoolsetEnd&gt;
              &lt;/index&gt;
              &lt;index name="LOTXML_PRINT" id="LOTXML_PRINT" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
                &lt;fileName fieldRef="PRINT_LOTXML_NAME" dataProvider="custom"/&gt;
                &lt;spoolsetEnd&gt;
                  &lt;record terminator="crlf" name="LOTXML Content" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;value fieldRef="PRINT_LOTXML_BODY_RE" dataProvider="custom"/&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/spoolsetEnd&gt;
              &lt;/index&gt;
              &lt;spoolfiles&gt;
                &lt;fileName fieldRef="PRINT_FILE_NAME" dataProvider="custom"/&gt;
              &lt;/spoolfiles&gt;
              &lt;security&gt;
                &lt;zipPasswordField fieldRef="PJAbsOutputPath" dataProvider="system"/&gt;
                &lt;enableZipPassword&gt;false&lt;/enableZipPassword&gt;
                &lt;requirePasswordToOpen&gt;true&lt;/requirePasswordToOpen&gt;
                &lt;passwordToOpen fieldRef="PWD_USER_DATAFILE" dataProvider="custom"/&gt;
                &lt;requirePasswordToOp&gt;true&lt;/requirePasswordToOp&gt;
                &lt;passwordToOp fieldRef="PWD_OWNER_DATAFILE" dataProvider="custom"/&gt;
                &lt;allowPrinting&gt;false&lt;/allowPrinting&gt;
                &lt;allowEditing&gt;true&lt;/allowEditing&gt;
                &lt;allowCopying&gt;false&lt;/allowCopying&gt;
                &lt;allowAnnotationEditing&gt;false&lt;/allowAnnotationEditing&gt;
              &lt;/security&gt;
              &lt;spoolfilesettings enableFillerPages="false" fillerPagesPerPrint="2" startShipmentOnPage="2"&gt;
                &lt;fillerPagesActivationAttribute/&gt;
              &lt;/spoolfilesettings&gt;
              &lt;outputPackaging enabled="false" afterEntity="shipment" enableCrypt="false" compressionMethod="zip"&gt;
                &lt;outputFileName/&gt;
                &lt;outputPassword/&gt;
                &lt;sourceFolder/&gt;
              &lt;/outputPackaging&gt;
            &lt;/spoolset&gt;
          &lt;/spoolsets&gt;
          &lt;lotMD enabled="true"&gt;
            &lt;path/&gt;
            &lt;filename/&gt;
            &lt;producer&gt;
              &lt;bomId/&gt;
              &lt;environmentDn/&gt;
              &lt;useCase&gt;ONDEMAND&lt;/useCase&gt;
            &lt;/producer&gt;
            &lt;externalId/&gt;
            &lt;priority&gt;LOWEST&lt;/priority&gt;
            &lt;messages&gt;
              &lt;message&gt;
                &lt;gateways&gt;
                  &lt;email enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/email&gt;
                  &lt;pec enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/pec&gt;
                  &lt;sms enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients&gt;
                      &lt;recipient&gt;
                        &lt;address/&gt;
                        &lt;name/&gt;
                        &lt;type&gt;TO&lt;/type&gt;
                      &lt;/recipient&gt;
                    &lt;/recipients&gt;
                    &lt;body&gt;
                      &lt;text&gt;
                        &lt;path/&gt;
                      &lt;/text&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/sms&gt;
                  &lt;purl enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/purl&gt;
                  &lt;fax enabled="false"&gt;
                    &lt;destination/&gt;
                    &lt;files&gt;
                      &lt;file&gt;
                        &lt;remoteSubpath/&gt;
                        &lt;path/&gt;
                      &lt;/file&gt;
                    &lt;/files&gt;
                    &lt;sender/&gt;
                    &lt;quality&gt;medium&lt;/quality&gt;
                  &lt;/fax&gt;
                  &lt;fileshare enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;
                    &lt;remoteSubpath/&gt;
                    &lt;files/&gt;
                  &lt;/fileshare&gt;
                  &lt;ftp enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;
                    &lt;remoteSubpath/&gt;
                    &lt;files/&gt;
                  &lt;/ftp&gt;
                &lt;/gateways&gt;
                &lt;properties&gt;
                  &lt;property name="ID_OBJECT"&gt;
                    &lt;value/&gt;
                  &lt;/property&gt;
                &lt;/properties&gt;
              &lt;/message&gt;
            &lt;/messages&gt;
          &lt;/lotMD&gt;
          &lt;DAConfiguration enabled="false"/&gt;
        &lt;/fileManagementConfiguration&gt;
        &lt;fileManagementConfiguration id="EMAIL" name="EMAIL" errorManagement="stop" spoolingOnError="true" reduceWorkingSpace="true"&gt;
          &lt;printjob&gt;
            &lt;index name="TRACKING550" id="TRACKING550E" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="TR550_FILENAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_02_LOTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_03_CLIENTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_04_ACCOUNTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_05_JOBID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_06_WORKTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_07_WORKSTAGE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_08_OWNER" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_09_HOSTNAME" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_10_APPTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_11_PROCEDURE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_12_PROCVERS" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_13_JOBRESULT" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_14_AUTOCLOSE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_15_CUSTOM01" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_16_CUSTOM02" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_17_CUSTOM03" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_18_CUSTOM04" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_19_CUSTOM05" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_02_ID_ISTANZA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_04_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_05_NOME_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_06_SIZE_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_07_CODICE_P_E" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_08_ID_CONTAIN" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_09_NOME_CONTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_10_TS_CREAZIO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_12_FILENAME" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_13_FILEPATH" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_14_FILE_SIZE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_15_FILE_TYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_16_ID_PROD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_17_TS_INIZIO_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_18_TS_FINE_JO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_19_RECORD_STA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_20_RECORD_END" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_21_PROGRESSIV" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_22_PROGRESSIV" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_23_DOCUMENTI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_24_PAGINE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_25_PAGINE_BIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_26_FOGLI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_27_BOLLETTINI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_28_VIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_29_CAP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_30_LOCALITA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_31_PROVINCIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_32_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_33_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_34_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_35_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_36_TIPO_DOCUM" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_37_CANALE_E" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_38_FORMATO_E" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_39_EMISSIONE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_40_SOCIETA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_41_DIVISIONE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_42_MERCATO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_43_IMPORTO_TO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_44_CODICE_MOD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_45_CODICE_COL" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_46_CODICE_DUP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_47_NUMRACCAND" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_48_NUMRACCRIT" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_49_BARCODE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_50_AREA_POSTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_51_PESO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_52_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_53_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_54_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_55_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_56_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_57_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_58_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_59_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_60_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_61_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_62_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_63_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_64_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_65_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_66_ID_SUB_PRO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_67_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;index name="TRACKING560" id="TRACKING560E" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="TR560_FILENAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_01_ID_BUSTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_02_ID_DOCUMEN" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_03_CODICE_MOD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_04_TIPOLOGIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_05_ID_ACQUISI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_06_DATA_SCADE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_07_DATA_EMISS" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_08_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_09_CODICE_DES" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_10_NOME_DESTI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_11_PIVACF_DES" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_12_IMPORTO_PA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_13_PESO_DOCUM" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_14_PRESENZA_B" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_15_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;dataTracing enabled="false" respectBreakRules="false"&gt;
              &lt;dataTraceFile/&gt;
            &lt;/dataTracing&gt;
          &lt;/printjob&gt;
          &lt;spoolsets multiple="false"&gt;
            &lt;spoolset splitResolution="envelope" id="DEFAULT" suppressBackPages="false" trailingSheet="false" leadingSheet="false"&gt;
              &lt;index name="LOTXML" id="LOTXML" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
                &lt;fileName fieldRef="EMAIL_LOTXML_NAME" dataProvider="custom"/&gt;
                &lt;envelopeEnd&gt;
                  &lt;record terminator="crlf" name="Lotxml message" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;value fieldRef="EMAIL_LOTXML_BODY_RE" dataProvider="custom"/&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/envelopeEnd&gt;
                &lt;spoolsetStart&gt;
                  &lt;record terminator="crlf" name="Lotxml header" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;value fieldRef="EMAIL_LOTXML_HEADER" dataProvider="custom"/&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/spoolsetStart&gt;
                &lt;spoolsetEnd&gt;
                  &lt;record terminator="crlf" name="Lotxml footer" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;value fieldRef="EMAIL_LOTXML_FOOT_RE" dataProvider="custom"/&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/spoolsetEnd&gt;
              &lt;/index&gt;
              &lt;index name="SME_FILE_EMAIL" id="SME_FILE_EMAIL" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
                &lt;fileName fieldRef="EMAIL_SEMAPHORE_NAME" dataProvider="custom"/&gt;
                &lt;spoolsetEnd&gt;
                  &lt;record terminator="crlf" name="new record" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;const&gt;c21l&lt;/const&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/spoolsetEnd&gt;
              &lt;/index&gt;
              &lt;spoolfiles&gt;
                &lt;fileName fieldRef="EMAIL_SPOOL_NAME" dataProvider="custom"/&gt;
                &lt;index name="EMAIL_BODY" id="EMAIL_BODY" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
                  &lt;fileName fieldRef="EMAIL_BODY_NAME" dataProvider="custom"/&gt;
                  &lt;spoolfileEnd&gt;
                    &lt;record terminator="crlf" name="new record" groupable="0" useEnabling="false"&gt;
                      &lt;appendMode&gt;
                        &lt;variableLength/&gt;
                      &lt;/appendMode&gt;
                      &lt;enablingAttribute/&gt;
                      &lt;items&gt;
                        &lt;item&gt;
                          &lt;value fieldRef="EMAIL_BODY_CONT_RE" dataProvider="custom"/&gt;
                        &lt;/item&gt;
                      &lt;/items&gt;
                    &lt;/record&gt;
                  &lt;/spoolfileEnd&gt;
                &lt;/index&gt;
              &lt;/spoolfiles&gt;
              &lt;security&gt;
                &lt;zipPasswordField/&gt;
                &lt;enableZipPassword&gt;false&lt;/enableZipPassword&gt;
                &lt;requirePasswordToOpen&gt;false&lt;/requirePasswordToOpen&gt;
                &lt;passwordToOpen/&gt;
                &lt;requirePasswordToOp&gt;false&lt;/requirePasswordToOp&gt;
                &lt;passwordToOp/&gt;
                &lt;allowPrinting&gt;true&lt;/allowPrinting&gt;
                &lt;allowEditing&gt;true&lt;/allowEditing&gt;
                &lt;allowCopying&gt;true&lt;/allowCopying&gt;
                &lt;allowAnnotationEditing&gt;true&lt;/allowAnnotationEditing&gt;
              &lt;/security&gt;
              &lt;spoolfilesettings enableFillerPages="false" fillerPagesPerPrint="2" startShipmentOnPage="2"&gt;
                &lt;fillerPagesActivationAttribute/&gt;
              &lt;/spoolfilesettings&gt;
              &lt;outputPackaging enabled="false" afterEntity="shipment" enableCrypt="false" compressionMethod="zip"&gt;
                &lt;outputFileName/&gt;
                &lt;outputPassword/&gt;
                &lt;sourceFolder/&gt;
              &lt;/outputPackaging&gt;
            &lt;/spoolset&gt;
          &lt;/spoolsets&gt;
          &lt;lotMD enabled="false"&gt;
            &lt;path/&gt;
            &lt;filename/&gt;
            &lt;producer&gt;
              &lt;bomId/&gt;
              &lt;environmentDn/&gt;
              &lt;useCase&gt;ONDEMAND&lt;/useCase&gt;
            &lt;/producer&gt;
            &lt;externalId/&gt;
            &lt;priority&gt;LOWEST&lt;/priority&gt;
            &lt;messages&gt;
              &lt;message&gt;
                &lt;gateways&gt;
                  &lt;email enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/email&gt;
                  &lt;pec enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/pec&gt;
                  &lt;sms enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;text&gt;
                        &lt;path/&gt;
                      &lt;/text&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/sms&gt;
                  &lt;purl enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/purl&gt;
                  &lt;fax enabled="false"&gt;
                    &lt;destination/&gt;
                    &lt;files&gt;
                      &lt;file&gt;
                        &lt;remoteSubpath/&gt;
                        &lt;path/&gt;
                      &lt;/file&gt;
                    &lt;/files&gt;
                    &lt;sender/&gt;
                    &lt;quality&gt;medium&lt;/quality&gt;
                  &lt;/fax&gt;
                  &lt;fileshare enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;
                    &lt;remoteSubpath/&gt;
                    &lt;files/&gt;
                  &lt;/fileshare&gt;
                  &lt;ftp enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;
                    &lt;remoteSubpath/&gt;
                    &lt;files/&gt;
                  &lt;/ftp&gt;
                &lt;/gateways&gt;
                &lt;properties&gt;
                  &lt;property name="ID_OBJECT"&gt;
                    &lt;value/&gt;
                  &lt;/property&gt;
                &lt;/properties&gt;
              &lt;/message&gt;
            &lt;/messages&gt;
          &lt;/lotMD&gt;
          &lt;DAConfiguration enabled="false"/&gt;
        &lt;/fileManagementConfiguration&gt;
        &lt;fileManagementConfiguration id="ARCHIVE" name="ARCHIVE" errorManagement="stop" spoolingOnError="true" reduceWorkingSpace="true"&gt;
          &lt;printjob&gt;
            &lt;index name="TRACKING550" id="TRACKING550A" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="TR550_FILENAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_02_LOTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_03_CLIENTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_04_ACCOUNTID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_05_JOBID" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_06_WORKTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_07_WORKSTAGE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_08_OWNER" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_09_HOSTNAME" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_10_APPTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_11_PROCEDURE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_12_PROCVERS" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_13_JOBRESULT" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_14_AUTOCLOSE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_15_CUSTOM01" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_16_CUSTOM02" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_17_CUSTOM03" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_18_CUSTOM04" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550H_19_CUSTOM05" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_02_ID_ISTANZA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_04_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_05_NOME_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_06_SIZE_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_07_CODICE_P_A" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_08_ID_CONTAIN" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_09_NOME_CONTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_10_TS_CREAZIO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_12_FILENAME" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_13_FILEPATH" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_14_FILE_SIZE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_15_FILE_TYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_16_ID_PROD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_17_TS_INIZIO_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_18_TS_FINE_JO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_19_RECORD_STA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_20_RECORD_END" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_21_PROGRESSIV" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_22_PROGRESSIV" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_23_DOCUMENTI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_24_PAGINE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_25_PAGINE_BIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_26_FOGLI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_27_BOLLETTINI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_28_VIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_29_CAP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_30_LOCALITA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_31_PROVINCIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_32_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_33_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_34_ANAGRAFICA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_35_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_36_TIPO_DOCUM" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_37_CANALE_A" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_38_FORMATO_A" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_39_EMISSIONE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_40_SOCIETA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_41_DIVISIONE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_42_MERCATO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_43_IMPORTO_TO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_44_CODICE_MOD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_45_CODICE_COL" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_46_CODICE_DUP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_47_NUMRACCAND" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_48_NUMRACCRIT" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_49_BARCODE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_50_AREA_POSTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_51_PESO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_52_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_53_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_54_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_55_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_56_ALLEGATI_T" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_57_NUM_ALLEGA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_58_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_59_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_60_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_61_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_62_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_63_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_64_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_65_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_66_ID_SUB_PRO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR550D_67_CUSTOM_VC_" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;index name="TRACKING560" id="TRACKING560A" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="TR560_FILENAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength&gt;
                      &lt;separator&gt;fA==&lt;/separator&gt;
                    &lt;/variableLength&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_00_RECORDTYPE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_01_ID_BUSTA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_02_ID_DOCUMEN" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_03_CODICE_MOD" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_04_TIPOLOGIA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_05_ID_ACQUISI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_06_DATA_SCADE" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_07_DATA_EMISS" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_08_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_09_CODICE_DES" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_10_NOME_DESTI" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_11_PIVACF_DES" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_12_IMPORTO_PA" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_13_PESO_DOCUM" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_14_PRESENZA_B" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560D_15_CODICE_DOC" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;index name="DOCLIST" id="DOCLIST" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
              &lt;fileName fieldRef="DOCLIST_FILE_NAME" dataProvider="custom"/&gt;
              &lt;printjobStart&gt;
                &lt;record terminator="crlf" name="&amp;lt;?xml" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength/&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iSVNPODg1OS0xIiBzdGFuZGFsb25lPSJubyI/
Pg==&lt;/const&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
                &lt;record terminator="crlf" name="&amp;lt;doclist&gt;" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength/&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;const&gt;PGRvY2xpc3QgdGltZXN0YW1wPSI=&lt;/const&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="PJStartTimestamp" dataProvider="system"/&gt;
                    &lt;/item&gt;
                    &lt;item&gt;
                      &lt;const&gt;Ij4=&lt;/const&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobStart&gt;
              &lt;printjobEnd&gt;
                &lt;record terminator="crlf" name="&amp;lt;/doclist&gt;" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength/&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;const&gt;PC9kb2NsaXN0Pg==&lt;/const&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/printjobEnd&gt;
              &lt;documentEnd&gt;
                &lt;record terminator="crlf" name="&amp;lt;document/&gt;" groupable="0" useEnabling="false"&gt;
                  &lt;appendMode&gt;
                    &lt;variableLength/&gt;
                  &lt;/appendMode&gt;
                  &lt;enablingAttribute/&gt;
                  &lt;items&gt;
                    &lt;item&gt;
                      &lt;value fieldRef="DOCLIST_DOCUMENT_REP" dataProvider="custom"/&gt;
                    &lt;/item&gt;
                  &lt;/items&gt;
                &lt;/record&gt;
              &lt;/documentEnd&gt;
            &lt;/index&gt;
            &lt;dataTracing enabled="false" respectBreakRules="false"&gt;
              &lt;dataTraceFile/&gt;
            &lt;/dataTracing&gt;
          &lt;/printjob&gt;
          &lt;spoolsets multiple="false"&gt;
            &lt;spoolset splitResolution="document" id="DEFAULT" suppressBackPages="false" trailingSheet="false" leadingSheet="false"&gt;
              &lt;index name="LOTXML_ARCHIVE" id="LOTXML_ARCHIVE" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;
                &lt;fileName fieldRef="ARCH_LOTXML_NAME" dataProvider="custom"/&gt;
                &lt;spoolsetEnd&gt;
                  &lt;record terminator="crlf" name="LOTXML Content" groupable="0" useEnabling="false"&gt;
                    &lt;appendMode&gt;
                      &lt;variableLength/&gt;
                    &lt;/appendMode&gt;
                    &lt;enablingAttribute/&gt;
                    &lt;items&gt;
                      &lt;item&gt;
                        &lt;value fieldRef="ARCH_LOTXML_BODY_RE" dataProvider="custom"/&gt;
                      &lt;/item&gt;
                    &lt;/items&gt;
                  &lt;/record&gt;
                &lt;/spoolsetEnd&gt;
              &lt;/index&gt;
              &lt;spoolfiles&gt;
                &lt;fileName fieldRef="ARCH_SPOOL_NAME" dataProvider="custom"/&gt;
              &lt;/spoolfiles&gt;
              &lt;security&gt;
                &lt;zipPasswordField/&gt;
                &lt;enableZipPassword&gt;false&lt;/enableZipPassword&gt;
                &lt;requirePasswordToOpen&gt;false&lt;/requirePasswordToOpen&gt;
                &lt;passwordToOpen fieldRef="OWNER_PW" dataProvider="custom"/&gt;
                &lt;requirePasswordToOp&gt;false&lt;/requirePasswordToOp&gt;
                &lt;passwordToOp fieldRef="USER_PW" dataProvider="custom"/&gt;
                &lt;allowPrinting&gt;true&lt;/allowPrinting&gt;
                &lt;allowEditing&gt;true&lt;/allowEditing&gt;
                &lt;allowCopying&gt;true&lt;/allowCopying&gt;
                &lt;allowAnnotationEditing&gt;true&lt;/allowAnnotationEditing&gt;
              &lt;/security&gt;
              &lt;spoolfilesettings enableFillerPages="false" fillerPagesPerPrint="2" startShipmentOnPage="2"&gt;
                &lt;fillerPagesActivationAttribute/&gt;
              &lt;/spoolfilesettings&gt;
              &lt;outputPackaging enabled="false" afterEntity="shipment" enableCrypt="false" compressionMethod="zip"&gt;
                &lt;outputFileName/&gt;
                &lt;outputPassword/&gt;
                &lt;sourceFolder/&gt;
              &lt;/outputPackaging&gt;
            &lt;/spoolset&gt;
          &lt;/spoolsets&gt;
          &lt;lotMD enabled="false"&gt;
            &lt;path/&gt;
            &lt;filename/&gt;
            &lt;producer&gt;
              &lt;bomId/&gt;
              &lt;environmentDn/&gt;
              &lt;useCase&gt;ONDEMAND&lt;/useCase&gt;
            &lt;/producer&gt;
            &lt;externalId/&gt;
            &lt;priority&gt;LOWEST&lt;/priority&gt;
            &lt;messages&gt;
              &lt;message&gt;
                &lt;gateways&gt;
                  &lt;email enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/email&gt;
                  &lt;pec enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/pec&gt;
                  &lt;sms enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;text&gt;
                        &lt;path/&gt;
                      &lt;/text&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/sms&gt;
                  &lt;purl enabled="false"&gt;
                    &lt;codepage&gt;UTF-8&lt;/codepage&gt;
                    &lt;subject/&gt;
                    &lt;recipients/&gt;
                    &lt;body&gt;
                      &lt;html&gt;
                        &lt;path/&gt;
                      &lt;/html&gt;
                    &lt;/body&gt;
                    &lt;attachments/&gt;
                    &lt;from&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/from&gt;
                    &lt;replyTo&gt;
                      &lt;address/&gt;
                      &lt;name/&gt;
                    &lt;/replyTo&gt;
                    &lt;priority&gt;NORMAL&lt;/priority&gt;
                    &lt;x-headers/&gt;
                    &lt;emailUsername/&gt;
                    &lt;emailPassword/&gt;
                    &lt;emailMessageId/&gt;
                  &lt;/purl&gt;
                  &lt;fax enabled="false"&gt;
                    &lt;destination/&gt;
                    &lt;files&gt;
                      &lt;file&gt;
                        &lt;remoteSubpath/&gt;
                        &lt;path/&gt;
                      &lt;/file&gt;
                    &lt;/files&gt;
                    &lt;sender/&gt;
                    &lt;quality&gt;medium&lt;/quality&gt;
                  &lt;/fax&gt;
                  &lt;fileshare enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;
                    &lt;remoteSubpath/&gt;
                    &lt;files/&gt;
                  &lt;/fileshare&gt;
                  &lt;ftp enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;
                    &lt;remoteSubpath/&gt;
                    &lt;files/&gt;
                  &lt;/ftp&gt;
                &lt;/gateways&gt;
                &lt;properties&gt;
                  &lt;property name="ID_OBJECT"&gt;
                    &lt;value/&gt;
                  &lt;/property&gt;
                &lt;/properties&gt;
              &lt;/message&gt;
            &lt;/messages&gt;
          &lt;/lotMD&gt;
          &lt;DAConfiguration enabled="false"/&gt;
        &lt;/fileManagementConfiguration&gt;
      &lt;/fileManagement&gt;
      &lt;overprintManagement&gt;
        &lt;overprintManagementConfiguration id="PRINT" name="PRINT"&gt;
          &lt;printjob&gt;
            &lt;document&gt;
              &lt;allSheets/&gt;
              &lt;firstSheet&gt;
                &lt;front&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiID8+CjxyZXNvdXJjZSBsaWJyYXJ5
X2lkPSIwIiBleGFjdEhlaWdodD0iMTY5NTQ5IiBleGFjdFdpZHRoPSI5Mzk1MCIgd2lyZWZyYW1l
SGVpZ2h0PSIxNjk1NDkiIHdpcmVmcmFtZVdpZHRoPSI5Mzk1MCI+CiAgPHN3aW1sYW5lIGhlaWdo
dD0iMTY5NTQ5IiB5PSIwIj4KICAgIDxlbGVtZW50IHg9IjIzMDAwIiB5PSIyNjgyOCIgd2lkdGg9
IjcwOTUwIiBoZWlnaHQ9IjE0NzMyIiBvcmRlcj0iMSIgaWQ9IjAuMjM2NzM0Njc2NjQwNDgwNzYi
IGRlYnVnPSJmYWxzZSIgcm90YXRpb249IjAiPgogICAgICA8ZHJhdz4KICAgICAgICA8YmFyY29k
ZSB2YXJkYXRhSWQ9IjU5NCIgdmFyZGF0YVBsYWNlaG9sZGVyPSJJTUJfVkFMVUUiIHR5cGVJZD0i
MyIgZmFtaWx5PSIxZCIgdHlwZT0iaW1iIiByZW5kZXJzdHJpbmc9IlxcQmVnaW57NFNUQVRFfVxc
bV9uQmFyQ29kZUlEezcwNX1cXG1fbkJhckNvZGVUeXBlezN9XFxtX3N6VGV4dHswMTIzNDU2NzA5
NDk4NzY1NDMyMTAxMjM0NTY3ODkxfVxcbV9uVGV4dExlbmd0aHszMX1cXG1fY1Byb21wdENoYXJ7
MTIwfVxcbV9uTWVhc3VyZVR5cGV7Mn1cXG1fblByaW50ZXJSZXNvbHV0aW9uezMwMH1cXG1fbkhl
aWdodEluRG90c3s0NH1cXG1fbldpZHRoSW5Eb3RzezgzOH1cXG1fbkJhcldpZHRoezUwfVxcbV9u
QXNjZW5kZXJIZWlnaHR7MTIzfVxcbV9uVHJhY2tIZWlnaHR7MTIxfVxcbV9uRGVzY2VuZGVySGVp
Z2h0ezEyM31cXG1fbkJhclBpdGNoezIyfVxcbV9uRW5jb2RpbmdUYWJsZXstMX1cXG1fbkZDQ3st
MX1cXEVuZHs0U1RBVEV9IiBhbGxvd0hlaWdodENoYW5nZT0idHJ1ZSIgYWxsb3dlZERhdGFUeXBl
PSJudW1lcmljb25seSIgYWxsb3dPZGRDaGFycz0iZmFsc2UiIG1pbkxlbmd0aD0iMzIiIG1heExl
bmd0aD0iMzIiLz4KICAgICAgPC9kcmF3PgogICAgPC9lbGVtZW50PgogICAgPGVsZW1lbnQgeD0i
MCIgeT0iNzk1NDkiIHdpZHRoPSIxMDAwMCIgaGVpZ2h0PSIxMDAwMCIgb3JkZXI9IjIiIGlkPSIw
LjYwOTQyMDQ3NzQxMjY0MSIgZGVidWc9InRydWUiIHJvdGF0aW9uPSIwIj4KICAgICAgPGRyYXcg
c3Ryb2tlPSJmYWxzZSIgc3Ryb2tlQ29sb3I9IjB4MCIgc3Ryb2tlV2VpZ2h0PSIzMDAiPgogICAg
ICAgIDxiYXJzZXQgZ2FwPSIxMDAwMCIgd2VpZ2h0PSI2MDAiLz4KICAgICAgPC9kcmF3PgogICAg
PC9lbGVtZW50PgogIDwvc3dpbWxhbmU+CjwvcmVzb3VyY2U+&lt;/front&gt;
              &lt;/firstSheet&gt;
              &lt;lastSheet/&gt;
            &lt;/document&gt;
            &lt;envelope&gt;
              &lt;allSheets/&gt;
              &lt;firstSheet/&gt;
              &lt;lastSheet/&gt;
            &lt;/envelope&gt;
            &lt;header&gt;
              &lt;allSheets/&gt;
              &lt;firstSheet/&gt;
              &lt;lastSheet/&gt;
            &lt;/header&gt;
            &lt;trailer&gt;
              &lt;allSheets/&gt;
              &lt;firstSheet/&gt;
              &lt;lastSheet/&gt;
            &lt;/trailer&gt;
            &lt;fillerPage&gt;
              &lt;allSheets/&gt;
              &lt;firstSheet/&gt;
              &lt;lastSheet/&gt;
            &lt;/fillerPage&gt;
          &lt;/printjob&gt;
          &lt;lots&gt;
            &lt;lot lotId="DEFAULT"&gt;
              &lt;envelope&gt;
                &lt;allSheets/&gt;
                &lt;firstSheet/&gt;
                &lt;lastSheet/&gt;
              &lt;/envelope&gt;
            &lt;/lot&gt;
          &lt;/lots&gt;
        &lt;/overprintManagementConfiguration&gt;
      &lt;/overprintManagement&gt;
    &lt;/serializer&gt;
  &lt;/serializers&gt;
  &lt;omsf:fieldsConfig xmlns:omsf="http://www.ebilling.it/eDoc2/OutputManagementSystemFields" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"&gt;
    &lt;omsf:field varName="TargetCountry" varLen="2" name="Country code" entity="printjob" id="PJTargetCountry" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ConstantTrue" varLen="0" name="True (constant)" entity="printjob" id="PJConstantTrue" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ConstantFalse" varLen="0" name="False (constant)" entity="printjob" id="PJConstantFalse" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ConstantZero" varLen="0" name="Zero (constant)" entity="printjob" id="PJConstantZero" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ConstantStringNull" varLen="1" name="Character 0 (constant)" entity="printjob" id="PJConstantStringNull" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ColorModel" varLen="0" name="Color model code" entity="printjob" id="PJColorModel" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DuplexPrint" varLen="0" name="Duplexing print enabled" entity="printjob" id="PJDuplexPrint" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EmitterCode" varLen="0" name="Emitter code" entity="printjob" id="PJEmitterCode" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileExtension" varLen="10" name="Spoolfile extension (without dot)." entity="printjob" id="PJSpoolfileExtension" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotId" varLen="256" name="External lot identifier" entity="printjob" id="PJLotId" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="JobId" varLen="256" name="External job identifier" entity="printjob" id="PJJobId" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SerializerId" varLen="50" name="External serializer identifier" entity="printjob" id="PJSerializerId" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FileManagementId" varLen="50" name="External file management identifier" entity="printjob" id="PJFileManagementId" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="OverprintId1" varLen="50" name="External overprint layer 1 identifier" entity="printjob" id="PJOverprintId1" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="OverprintId2" varLen="50" name="External overprint layer 2 identifier" entity="printjob" id="PJOverprintId2" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="OverprintId3" varLen="50" name="External overprint layer 3 identifier" entity="printjob" id="PJOverprintId3" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="OverprintId4" varLen="50" name="External overprint layer 4 identifier" entity="printjob" id="PJOverprintId4" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField1" varLen="10240" name="External custom field 1" entity="printjob" id="PJePublishCustomField1" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField2" varLen="10240" name="External custom field 2" entity="printjob" id="PJePublishCustomField2" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField3" varLen="10240" name="External custom field 3" entity="printjob" id="PJePublishCustomField3" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField4" varLen="10240" name="External custom field 4" entity="printjob" id="PJePublishCustomField4" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField5" varLen="10240" name="External custom field 5" entity="printjob" id="PJePublishCustomField5" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField6" varLen="10240" name="External custom field 6" entity="printjob" id="PJePublishCustomField6" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField7" varLen="10240" name="External custom field 7" entity="printjob" id="PJePublishCustomField7" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField8" varLen="10240" name="External custom field 8" entity="printjob" id="PJePublishCustomField8" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField9" varLen="10240" name="External custom field 9" entity="printjob" id="PJePublishCustomField9" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ePublishCustomField10" varLen="10240" name="External custom field 10" entity="printjob" id="PJePublishCustomField10" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="StartTimestamp" varLen="14" name="Process-start timestamp" entity="printjob" id="PJStartTimestamp" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EndTimestamp" varLen="14" name="Process-end timestamp" entity="printjob" id="PJEndTimestamp" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DataFullFileName" varLen="256" name="Input data full filename" entity="printjob" id="PJDataFullFileName" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DataFileName" varLen="256" name="Input data filename" entity="printjob" id="PJDataFileName" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Multispoolset" varLen="0" name="Multispoolset enabled" entity="printjob" id="PJMultiSpoolSet" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="AbsPath" varLen="256" name="Absolute output path" entity="printjob" id="PJAbsOutputPath" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalLots" varLen="0" name="Total lots" entity="printjob" id="PJTotalLots" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSpoolsets" varLen="0" name="Total spoolsets" entity="printjob" id="PJTotalSpoolsets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfilesCounter" varLen="0" name="Spoolfiles counter" entity="printjob" id="PJSpoolfilesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentsCounter" varLen="0" name="Shipments counter" entity="printjob" id="PJDocumentsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field type="number" varLen="0" id="PJTemplatesCounter" entity="printjob" varName="TemplatesCounter" name="Documents counter" createInstance="none" available="post"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="printjob" id="PJEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentsInErrorCounter" varLen="0" name="Shipments discarded counter" entity="printjob" id="PJDocumentsInErrorCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplatesInErrorCounter" varLen="0" name="Documents discarded counter" entity="printjob" id="PJTemplatesInErrorCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="printjob" id="PJPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="printjob" id="PJPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="printjob" id="PJFillPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="printjob" id="PJFillSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="printjob" id="PJCoverPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="printjob" id="PJCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="printjob" id="PJPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="printjob" id="PJSheetsCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="printjob" id="PJPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="printjob" id="PJSheetsCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="printjob" id="PJPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="printjob" id="PJSheetsCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="printjob" id="PJPagesCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="printjob" id="PJSheetsCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IndexesAbsPath" varLen="256" name="Indexes absolute path" entity="printjob" id="PJIndexesAbsPath" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IndexesRelPath" varLen="256" name="Indexes relative path" entity="printjob" id="PJIndexesRelPath" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FileName" varLen="256" name="Index filename" entity="printjob" id="PJIndexFileName" available="pre" createInstance="index" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FullFileName" varLen="256" name="Index full filename" entity="printjob" id="PJIndexFullFileName" available="pre" createInstance="index" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="RecsCount" varLen="0" name="Index records counter" entity="printjob" id="PJIndexRecsCount" available="pre" createInstance="index" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="printjob" id="PJPersonCoverExtraPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="printjob" id="PJPersCoverExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;cover pages counter" entity="printjob" id="PJPersonalizeCoverPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity="printjob" id="PJPersCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="printjob" id="PJExtraPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="printjob" id="PJExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="1PagesEnvelopesCounter" varLen="0" name="One-page envelopes counter" entity="printjob" id="PJ1PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="2PagesEnvelopesCounter" varLen="0" name="Two-pages envelopes counter" entity="printjob" id="PJ2PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="3PagesEnvelopesCounter" varLen="0" name="Three-pages envelopes counter" entity="printjob" id="PJ3PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="4PagesEnvelopesCounter" varLen="0" name="Four-pages envelopes counter" entity="printjob" id="PJ4PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="5PagesEnvelopesCounter" varLen="0" name="Five-pages envelopes counter" entity="printjob" id="PJ5PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="6PagesEnvelopesCounter" varLen="0" name="Six-pages envelopes counter" entity="printjob" id="PJ6PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="7PagesEnvelopesCounter" varLen="0" name="Seven-pages envelopes counter" entity="printjob" id="PJ7PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="8PagesEnvelopesCounter" varLen="0" name="Eight-pages envelopes counter" entity="printjob" id="PJ8PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9PagesEnvelopesCounter" varLen="0" name="Nine-pages envelopes counter" entity="printjob" id="PJ9PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9UpPagesEnvelopesCounter" varLen="0" name="More than nine-pages envelopes counter" entity="printjob" id="PJ9UpPagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="1SheetsEnvelopesCounter" varLen="0" name="One-sheet envelopes counter" entity="printjob" id="PJ1SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="2SheetsEnvelopesCounter" varLen="0" name="Two-sheets envelopes counter" entity="printjob" id="PJ2SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="3SheetsEnvelopesCounter" varLen="0" name="Three-sheets envelopes counter" entity="printjob" id="PJ3SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="4SheetsEnvelopesCounter" varLen="0" name="Four-sheets envelopes counter" entity="printjob" id="PJ4SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="5SheetsEnvelopesCounter" varLen="0" name="Five-sheets envelopes counter" entity="printjob" id="PJ5SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="6SheetsEnvelopesCounter" varLen="0" name="Six-sheets envelopes counter" entity="printjob" id="PJ6SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="7SheetsEnvelopesCounter" varLen="0" name="Seven-sheets envelopes counter" entity="printjob" id="PJ7SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="8SheetsEnvelopesCounter" varLen="0" name="Eight-sheets envelopes counter" entity="printjob" id="PJ8SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9SheetsEnvelopesCounter" varLen="0" name="Nine-sheets envelopes counter" entity="printjob" id="PJ9SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9UpSheetsEnvelopesCounter" varLen="0" name="More than nine-sheets envelopes counter" entity="printjob" id="PJ9UpSheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="printjob" id="PJEnvelopesCounter_Insert1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="printjob" id="PJEnvelopesCounter_Insert2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="printjob" id="PJEnvelopesCounter_Insert3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="printjob" id="PJEnvelopesCounter_Insert4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="printjob" id="PJSheetsCounter_Insert1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="printjob" id="PJSheetsCounter_Insert2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="printjob" id="PJSheetsCounter_Insert3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="printjob" id="PJSheetsCounter_Insert4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Id" varLen="50" name="Id" entity="lot" id="LotId" available="pre" createInstance="lot" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentsInErrorCounter" varLen="0" name="Shipments discarded counter" entity="lot" id="LotDocumentsInErrorCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplatesInErrorCounter" varLen="0" name="Documents discarded counter" entity="lot" id="LotTemplatesInErrorCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Enveloper3BitsGroupNumber" varLen="0" name="MailSystem envelope counter (3 bits)" entity="lot" id="LotEnveloper3BitsGroupNumber" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Enveloper4BitsGroupNumber" varLen="0" name="MailSystem envelope counter (4 bits)" entity="lot" id="LotEnveloper4BitsGroupNumber" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Enveloper5BitsGroupNumber" varLen="0" name="MailSystem envelope counter (5 bits)" entity="lot" id="LotEnveloper5BitsGroupNumber" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Enveloper3BitsSequenceNumber" varLen="0" name="MailSystem sheet counter (3 bits)" entity="lot" id="LotEnveloper3BitsSeqNumber" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Enveloper4BitsSequenceNumber" varLen="0" name="MailSystem sheet counter (4 bits)" entity="lot" id="LotEnveloper4BitsSeqNumber" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Enveloper5BitsSequenceNumber" varLen="0" name="MailSystem sheet counter (5 bits)" entity="lot" id="LotEnveloper5BitsSeqNumber" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Name" varLen="256" name="Name" entity="lot" id="LotName" available="pre" createInstance="lot" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="lot" id="LotPagesCounter_PAGETAG1" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="lot" id="LotSheetsCounter_PAGETAG1" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="lot" id="LotPagesCounter_PAGETAG2" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="lot" id="LotSheetsCounter_PAGETAG2" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="lot" id="LotPagesCounter_PAGETAG3" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="lot" id="LotSheetsCounter_PAGETAG3" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="lot" id="LotPagesCounter_PAGETAG4" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="lot" id="LotSheetsCounter_PAGETAG4" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="lot" id="LotEnvelopesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="lot" id="LotPersonalizedPagesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="lot" id="LotPersonalizedSheetsCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="lot" id="LotFillPagesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="lot" id="LotFillSheetsCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="lot" id="LotCoverPagesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="lot" id="LotCoverSheetsCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="lot" id="LotPersCoverExtraPagesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="lot" id="LotPersCoverExtraSheetsCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;Cover pages counter" entity="lot" id="LotPersCoverPagesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity="lot" id="LotPersCoverSheetsCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="lot" id="LotExtraPagesCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="lot" id="LotExtraSheetsCounter" available="post" createInstance="lot" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Id" varLen="50" name="Identifier" entity="spoolset" id="SSId" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentsInErrorCounter" varLen="0" name="Shipments discarded counter" entity="spoolset" id="SSDocumentsInErrorCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplatesInErrorCounter" varLen="0" name="Documents discarded counter" entity="spoolset" id="SSTemplatesInErrorCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotId" varLen="50" name="Lot identifier" entity="spoolset" id="SSLotId" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="AbsPath" varLen="256" name="Absolute path" entity="spoolset" id="SSAbsPath" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="RelPath" varLen="256" name="Relative path" entity="spoolset" id="SSRelPath" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IndexesAbsPath" varLen="256" name="Indexes absolute path" entity="spoolset" id="SSIndexesAbsPath" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IndexesRelPath" varLen="256" name="Indexes relative path" entity="spoolset" id="SSIndexesRelPath" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FileName" varLen="256" name="Index fileName" entity="spoolset" id="SSIndexFileName" available="pre" createInstance="index" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FullFileName" varLen="256" name="Index full filename" entity="spoolset" id="SSIndexFullFileName" available="pre" createInstance="index" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="RecsCount" varLen="0" name="Index records counter" entity="spoolset" id="SSIndexRecsCount" available="pre" createInstance="index" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CurrentSpoolfileIsOpen" varLen="0" name="Current spoolfile is open" entity="spoolset" id="SFfileIsOpen" available="pre" createInstance="spoolset" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SplitResolution" varLen="10" name="Split resolution" entity="spoolset" id="SSSplitResolution" available="pre" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SplitPageGroupSize" varLen="0" name="Split pagegroup size" entity="spoolset" id="SSSplitPageGroupSize" available="pre" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfilesCounter" varLen="0" name="Spoolfiles counter" entity="spoolset" id="SSSpoolfilesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="spoolset" id="SSEnvelopesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="spoolset" id="SSPersPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="spoolset" id="SSPersSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="spoolset" id="SSFillPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="spoolset" id="SSFillSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="spoolset" id="SSCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="spoolset" id="SSCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="spoolset" id="SSPersCoverExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="spoolset" id="SSPersCoverExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity="spoolset" id="SSPersCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;Cover pages counter" entity="spoolset" id="SSPersCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="spoolset" id="SSExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="spoolset" id="SSExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="spoolset" id="SSPagesCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="spoolset" id="SSSheetsCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="spoolset" id="SSPagesCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="spoolset" id="SSSheetsCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="spoolset" id="SSPagesCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="spoolset" id="SSSheetsCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="spoolset" id="SSPagesCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="spoolset" id="SSSheetsCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="1PagesEnvelopesCounter" varLen="0" name="One-page envelopes counter" entity="spoolset" id="SS1PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="2PagesEnvelopesCounter" varLen="0" name="Two-pages envelopes counter" entity="spoolset" id="SS2PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="3PagesEnvelopesCounter" varLen="0" name="Three-pages envelopes counter" entity="spoolset" id="SS3PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="4PagesEnvelopesCounter" varLen="0" name="Four-pages envelopes counter" entity="spoolset" id="SS4PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="5PagesEnvelopesCounter" varLen="0" name="Five-pages envelopes counter" entity="spoolset" id="SS5PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="6PagesEnvelopesCounter" varLen="0" name="Six-pages envelopes counter" entity="spoolset" id="SS6PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="7PagesEnvelopesCounter" varLen="0" name="Seven-pages envelopes counter" entity="spoolset" id="SS7PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="8PagesEnvelopesCounter" varLen="0" name="Eight-pages envelopes counter" entity="spoolset" id="SS8PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9PagesEnvelopesCounter" varLen="0" name="Nine-pages envelopes counter" entity="spoolset" id="SS9PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9UpPagesEnvelopesCounter" varLen="0" name="More than nine-pages envelopes counter" entity="spoolset" id="SS9UpPagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="1SheetsEnvelopesCounter" varLen="0" name="One-sheet envelopes counter" entity="spoolset" id="SS1SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="2SheetsEnvelopesCounter" varLen="0" name="Two-sheets envelopes counter" entity="spoolset" id="SS2SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="3SheetsEnvelopesCounter" varLen="0" name="Three-sheets envelopes counter" entity="spoolset" id="SS3SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="4SheetsEnvelopesCounter" varLen="0" name="Four-sheets envelopes counter" entity="spoolset" id="SS4SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="5SheetsEnvelopesCounter" varLen="0" name="Five-sheets envelopes counter" entity="spoolset" id="SS5SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="6SheetsEnvelopesCounter" varLen="0" name="Six-sheets envelopes counter" entity="spoolset" id="SS6SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="7SheetsEnvelopesCounter" varLen="0" name="Seven-sheets envelopes counter" entity="spoolset" id="SS7SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="8SheetsEnvelopesCounter" varLen="0" name="Eight-sheets envelopes counter" entity="spoolset" id="SS8SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9SheetsEnvelopesCounter" varLen="0" name="Nine-sheets envelopes counter" entity="spoolset" id="SS9SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9UpSheetsEnvelopesCounter" varLen="0" name="More than nine-sheets envelopes counter" entity="spoolset" id="SS9UpSheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="HeaderSheetEnabled" varLen="0" name="Header sheet enabling flag" entity="spoolset" id="HeaderSheetEnabled" available="pre" createInstance="spoolset" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TrailerSheetEnabled" varLen="0" name="Trailer sheet enabling flag" entity="spoolset" id="TrailerSheetEnabled" available="pre" createInstance="spoolset" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="spoolset" id="SSEnvelopesCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="spoolset" id="SSEnvelopesCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="spoolset" id="SSEnvelopesCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="spoolset" id="SSEnvelopesCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="spoolset" id="SSSheetsCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="spoolset" id="SSSheetsCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="spoolset" id="SSSheetsCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="spoolset" id="SSSheetsCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field type="number" varLen="0" id="SSTemplatesCounter" entity="spoolset" varName="TemplatesCounter" name="Documents counter" createInstance="spoolset" available="post"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FileName" varLen="256" name="Filename" entity="spoolfile" id="SFFileName" available="post" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FullFileName" varLen="256" name="full filename" entity="spoolfile" id="SFFullFileName" available="post" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="AbsPath" varLen="256" name="Absolute path" entity="spoolfile" id="SFSpoolfilesAbsPath" available="post" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="RelPath" varLen="256" name="Relative path" entity="spoolfile" id="SFSpoolfilesRelPath" available="post" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IndexesAbsPath" varLen="256" name="Indexes absolute path" entity="spoolfile" id="SFIndexesAbsPath" available="post" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IndexesRelPath" varLen="256" name="Indexes relative path" entity="spoolfile" id="SFIndexesRelPath" available="post" createInstance="spoolset" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FileName" varLen="256" name="Index filename" entity="spoolfile" id="SFIndexFileName" available="post" createInstance="index" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FullFileName" varLen="256" name="Index full filename" entity="spoolfile" id="SFIndexFullFileName" available="post" createInstance="index" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="RecsCount" varLen="0" name="Index records counter" entity="spoolfile" id="SFIndexRecsCount" available="post" createInstance="index" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="spoolfile" id="SFEnvelopesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentsCounter" varLen="0" name="Shipments counter" entity="spoolfile" id="SFDocumentsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplatesCounter" varLen="0" name="Documents counter" entity="spoolfile" id="SFTemplatesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="spoolfile" id="SFPersonalizedPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="spoolfile" id="SFPersonalizedSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="spoolfile" id="SFFillPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="spoolfile" id="SFFillSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="spoolfile" id="SFCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="spoolfile" id="SFCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="spoolfile" id="SFPagesCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="spoolfile" id="SFSheetsCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="spoolfile" id="SFPagesCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="spoolfile" id="SFSheetsCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="spoolfile" id="SFPagesCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="spoolfile" id="SFSheetsCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="spoolfile" id="SFPagesCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="spoolfile" id="SFSheetsCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="spoolfile" id="SFPersCoverExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="spoolfile" id="SFPersCoverExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;Cover pages counter" entity="spoolfile" id="SFPersCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity="spoolfile" id="SFPersCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="spoolfile" id="SFExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="spoolfile" id="SFExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="1PagesEnvelopesCounter" varLen="0" name="One-page envelopes counter" entity="spoolfile" id="SF1PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="2PagesEnvelopesCounter" varLen="0" name="Two-pages envelopes counter" entity="spoolfile" id="SF2PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="3PagesEnvelopesCounter" varLen="0" name="Three-pages envelopes counter" entity="spoolfile" id="SF3PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="4PagesEnvelopesCounter" varLen="0" name="Four-pages envelopes counter" entity="spoolfile" id="SF4PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="5PagesEnvelopesCounter" varLen="0" name="Five-pages envelopes counter" entity="spoolfile" id="SF5PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="6PagesEnvelopesCounter" varLen="0" name="Six-pages envelopes counter" entity="spoolfile" id="SF6PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="7PagesEnvelopesCounter" varLen="0" name="Seven-pages envelopes counter" entity="spoolfile" id="SF7PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="8PagesEnvelopesCounter" varLen="0" name="Eight-pages envelopes counter" entity="spoolfile" id="SF8PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9PagesEnvelopesCounter" varLen="0" name="Nine-pages envelopes counter" entity="spoolfile" id="SF9PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9UpPagesEnvelopesCounter" varLen="0" name="More than nine-pages envelopes counter" entity="spoolfile" id="SF9UpPagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="1SheetsEnvelopesCounter" varLen="0" name="One-sheet envelopes counter" entity="spoolfile" id="SF1SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="2SheetsEnvelopesCounter" varLen="0" name="Two-sheets envelopes counter" entity="spoolfile" id="SF2SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="3SheetsEnvelopesCounter" varLen="0" name="Three-sheets envelopes counter" entity="spoolfile" id="SF3SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="4SheetsEnvelopesCounter" varLen="0" name="Four-sheets envelopes counter" entity="spoolfile" id="SF4SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="5SheetsEnvelopesCounter" varLen="0" name="Five-sheets envelopes counter" entity="spoolfile" id="SF5SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="6SheetsEnvelopesCounter" varLen="0" name="Six-sheets envelopes counter" entity="spoolfile" id="SF6SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="7SheetsEnvelopesCounter" varLen="0" name="Seven-sheets envelopes counter" entity="spoolfile" id="SF7SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="8SheetsEnvelopesCounter" varLen="0" name="Eight-sheets envelopes counter" entity="spoolfile" id="SF8SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9SheetsEnvelopesCounter" varLen="0" name="Nine-sheets envelopes counter" entity="spoolfile" id="SF9SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="9UpSheetsEnvelopesCounter" varLen="0" name="More than nine-sheets envelopes counter" entity="spoolfile" id="SF9UpSheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="spoolfile" id="SFEnvelopesCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="spoolfile" id="SFEnvelopesCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="spoolfile" id="SFEnvelopesCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="spoolfile" id="SFEnvelopesCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="spoolfile" id="SFSheetsCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="spoolfile" id="SFSheetsCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="spoolfile" id="SFSheetsCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="spoolfile" id="SFSheetsCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="KilobytesDimension" varLen="0" name="The dimension of spoolfile in kB" entity="spoolfile" id="SFkiloBytesDimension" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="MegaBytesDimension" varLen="0" name="The dimension of spoolfile in MB" entity="spoolfile" id="SFMegaBytesDimension" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeSheetsCapacity" varLen="0" name="Envelope sheets capacity" entity="document" id="DOEnvelopeSheetsCapacity" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="InError" varLen="0" name="Discarded shipment" entity="document" id="DOInError" available="post" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ShipmentErrorCode" varLen="4" name="Shipment discarded error code" entity="document" id="DOErrorCode" available="post" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ShipmentErrorMessage" varLen="1024" name="Shipment discarded error message" entity="document" id="DOErrorMessage" available="post" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FirstEnvelopePersonalizedSheetsCapacity" varLen="0" name="First envelope personalized sheets capacity" entity="document" id="DOFirstEnvPersSheetsCapacity" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="AllButFirstEnvelopePersonalizedSheetsCapacity" varLen="0" name="All but first envelope personalized sheets capacity" entity="document" id="DOAllButFirstEnvPersSheetsCap" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Multienvelopes" varLen="0" name="Multienvelopes enabled" entity="document" id="DOMultienvelopes" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="UseCover" varLen="0" name="Cover enabled" entity="document" id="DOUseCover" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverOnFirstEnvelope" varLen="0" name="First envelope cover enabled" entity="document" id="DOCoverOnFirstEnvelope" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PrintjobPos" varLen="0" name="Printjob position" entity="document" id="DOPrintjobPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DatafileStartPos" varLen="0" name="Datafile start position" entity="document" id="DODatafileStartPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DatafileEndPos" varLen="0" name="Datafile end position" entity="document" id="DODatafileEndPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Timestamp" varLen="14" name="Timestamp" entity="document" id="DOTimestamp" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalEnvelopes" varLen="0" name="Total envelopes" entity="document" id="DOTotalEnvelopes" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalTemplates" varLen="0" name="Total documents" entity="document" id="DOTotalTemplates" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="document" id="DOEnvelopesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplatesCounter" varLen="0" name="Documents counter" entity="document" id="DOTemplatesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedPages" varLen="0" name="Total personalized pages" entity="document" id="DOTotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedSheets" varLen="0" name="Total personalized sheets" entity="document" id="DOTotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFillPages" varLen="0" name="Total blank pages" entity="document" id="DOTotalFillPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFillSheets" varLen="0" name="Total blank sheets" entity="document" id="DOTotalFillSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalCoverPages" varLen="0" name="Total cover pages" entity="document" id="DOTotalCoverPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalCoverSheets" varLen="0" name="Total cover sheets" entity="document" id="DOTotalCoverSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFirstEnvelopePersonalizedPages" varLen="0" name="Total first envelope personalized pages" entity="document" id="DOTotalFirstEnvelopePersPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFirstEnvelopePersonalizedSheets" varLen="0" name="Total first envelope personalized sheets" entity="document" id="DOTotalFirstEnvelopePersSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalInterEnvelopePersonalizedPages" varLen="0" name="Total inter-envelope personalized pages" entity="document" id="DOTotalInterEnvelopePersPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalInterEnvelopePersonalizedSheets" varLen="0" name="Total inter-envelope personalized sheets" entity="document" id="DOTotalInterEnvelopePersSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalLastEnvelopePersonalizedPages" varLen="0" name="Total last envelope personalized pages" entity="document" id="DOTotalLastEnvelopePersPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalLastEnvelopePersonalizedSheets" varLen="0" name="Total last envelope personalized sheets" entity="document" id="DOTotalLastEnvelopePersSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFirstEnvelopeCoverPages" varLen="0" name="Total first envelope cover pages" entity="document" id="DOTotalFirstEnvelopeCoverPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFirstEnvelopeCoverSheets" varLen="0" name="Total first envelope cover sheets" entity="document" id="DOTotalFirstEnvCoverSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalAllButFirstEnvelopeCoverPages" varLen="0" name="Total all but first envelope cover pages" entity="document" id="DOTotalAllButFirstEnvCovPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalAllButFirstEnvelopeCoverSheets" varLen="0" name="Total all but first envelope cover sheets" entity="document" id="DOTotalAllButFirstEnvCovSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFirstEnvelopeExtraPages" varLen="0" name="Total first envelope extra pages" entity="document" id="DOTotalFirstEnvelopeExtraPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFirstEnvelopeExtraSheets" varLen="0" name="Total first envelope extra sheets" entity="document" id="DOTotalFirstEnvExtraSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalAllEnvelopesExtraPages" varLen="0" name="Total all envelopes extra pages" entity="document" id="DOTotalAllEnvExtraPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalAllEnvelopesExtraSheets" varLen="0" name="Total all envelopes extra sheets" entity="document" id="DOTotalAllEnvExtraSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPages_PAGETAG1" varLen="0" name="Total pages with page attribute 1" entity="document" id="DOTotalPages_PAGETAG1" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_PAGETAG1" varLen="0" name="Total sheets with page attribute 1" entity="document" id="DOTotalSheets_PAGETAG1" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPages_PAGETAG2" varLen="0" name="Total pages with page attribute 2" entity="document" id="DOTotalPages_PAGETAG2" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_PAGETAG2" varLen="0" name="Total sheets with page attribute 2" entity="document" id="DOTotalSheets_PAGETAG2" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPages_PAGETAG3" varLen="0" name="Total pages with page attribute 3" entity="document" id="DOTotalPages_PAGETAG3" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_PAGETAG3" varLen="0" name="Total sheets with page attribute 3" entity="document" id="DOTotalSheets_PAGETAG3" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPages_PAGETAG4" varLen="0" name="Total pages with page attribute 4" entity="document" id="DOTotalPages_PAGETAG4" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_PAGETAG4" varLen="0" name="Total sheets with page attribute 4" entity="document" id="DOTotalSheets_PAGETAG4" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="document" id="DOPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="document" id="DOSheetsCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="document" id="DOPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="document" id="DOSheetsCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="document" id="DOPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="document" id="DOSheetsCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="document" id="DOPagesCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="document" id="DOSheetsCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="document" id="DOPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="document" id="DOPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="document" id="DOFillPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="document" id="DOFillSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="document" id="DOCoverPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="document" id="DOCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverExtraPages" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra pages" entity="document" id="DOTotalPersCoverExtraPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverExtraSheets" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra sheets" entity="document" id="DOTotalPersCoverExtraSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverPages" varLen="0" name="Total personalized&amp;amp;cover pages" entity="document" id="DOTotalPersCoverPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverSheets" varLen="0" name="Total personalized&amp;amp;cover sheets" entity="document" id="DOTotalPersCoverSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalExtraPages" varLen="0" name="Total extra pages" entity="document" id="DOTotalExtraPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalExtraSheets" varLen="0" name="Total extra sheets" entity="document" id="DOTotalExtraSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="document" id="DOPersoCoverExtraPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="document" id="DOPersCoverExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;cover pages counter" entity="document" id="DOPersCoverPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;cover sheets counter" entity="document" id="DOPersCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="document" id="DOExtraPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="document" id="DOExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileSegmentCounter" varLen="0" name="Document spoolfiles counter" entity="document" id="DOSegmentCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="document" id="DOEnvelopesCounter_Insert1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="document" id="DOEnvelopesCounter_Insert2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="document" id="DOEnvelopesCounter_Insert3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="document" id="DOEnvelopesCounter_Insert4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalEnvelopes_Insert1" varLen="0" name="Total envelopes counter with insert 1" entity="document" id="DOTotalEnvelopes_Insert1" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalEnvelopes_Insert2" varLen="0" name="Total envelopes counter with insert 2" entity="document" id="DOTotalEnvelopes_Insert2" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalEnvelopes_Insert3" varLen="0" name="Total envelopes counter with insert 3" entity="document" id="DOTotalEnvelopes_Insert3" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalEnvelopes_Insert4" varLen="0" name="Total envelopes counter with insert 4" entity="document" id="DOTotalEnvelopes_Insert4" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="document" id="DOSheetsCounter_Insert1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="document" id="DOSheetsCounter_Insert2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="document" id="DOSheetsCounter_Insert3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="document" id="DOSheetsCounter_Insert4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert1" varLen="0" name="Total sheets insert 1" entity="document" id="DOTotalSheets_Insert1" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert2" varLen="0" name="Total sheets insert 2" entity="document" id="DOTotalSheets_Insert2" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert3" varLen="0" name="Total sheets insert 3" entity="document" id="DOTotalSheets_Insert3" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert4" varLen="0" name="Total sheets insert 4" entity="document" id="DOTotalSheets_Insert4" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeFirstPagePos" varLen="0" name="Envelope first page position" entity="template" id="TEEnvelopeFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="InError" varLen="0" name="Discarded document" entity="template" id="TEInError" available="post" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentErrorCode" varLen="4" name="Document discarded error code" entity="template" id="TEErrorCode" available="post" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentErrorMessage" varLen="1024" name="Document discarded error message" entity="template" id="TEErrorMessage" available="post" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeFirstSheetPos" varLen="0" name="Envelope first sheet position" entity="template" id="TEEnvelopeFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLastPagePos" varLen="0" name="Envelope last page position" entity="template" id="TEEnvelopeLastPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLastSheetPos" varLen="0" name="Envelope last sheet position" entity="template" id="TEEnvelopeLastSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotPos" varLen="0" name="Lot position" entity="template" id="TELotPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotFirstPagePos" varLen="0" name="Envelope lot first page position" entity="template" id="TEEnvLotFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotFirstSheetPos" varLen="0" name="Envelope lot first sheet position" entity="template" id="TEEnvLotFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotLastPagePos" varLen="0" name="Envelope lot last page position" entity="template" id="TEEnvLotLastPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotLastSheetPos" varLen="0" name="Envelope lot last sheet position" entity="template" id="TEEnvLotLastSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstPagePos" varLen="0" name="Lot first page position" entity="template" id="TELotFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstSheetPos" varLen="0" name="Lot first sheet position" entity="template" id="TELotFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotLastPagePos" varLen="0" name="Lot last page position" entity="template" id="TELotLastPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotLastSheetPos" varLen="0" name="Lot last sheet position" entity="template" id="TELotLastSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetPos" varLen="0" name="Spoolset position" entity="template" id="TESpoolsetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstPagePos" varLen="0" name="Spoolset first page position" entity="template" id="TESpoolsetFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstSheetPos" varLen="0" name="Spoolset first sheet position" entity="template" id="TESpoolsetFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetLastPagePos" varLen="0" name="Spoolset last page position" entity="template" id="TESpoolsetLastPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetLastSheetPos" varLen="0" name="Spoolset last sheet position" entity="template" id="TESpoolsetLastSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstPagePos" varLen="0" name="Spoolfile first page position" entity="template" id="TESpoolfileFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstSheetPos" varLen="0" name="Spoolfile first sheet position" entity="template" id="TESpoolfileFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileLastPagePos" varLen="0" name="Spoolfile last page position" entity="template" id="TESpoolfileLastPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileLastSheetPos" varLen="0" name="Spoolfile last sheet position" entity="template" id="TESpoolfileLastSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeFirstEmptyPagePos" varLen="0" name="Envelope first blank page position" entity="template" id="TEEnvelopeFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeFirstEmptySheetPos" varLen="0" name="Envelope first blank sheet position" entity="template" id="TEEnvelopeFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLastEmptyPagePos" varLen="0" name="Envelope last blank page position" entity="template" id="TEEnvelopeLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLastEmptySheetPos" varLen="0" name="Envelope last blank sheet position" entity="template" id="TEEnvelopeLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotFirstEmptyPagePos" varLen="0" name="Envelope lot first blank page position" entity="template" id="TEEnvLotFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotFirstEmptySheetPos" varLen="0" name="Envelope lot first blank sheet position" entity="template" id="TEEnvLotFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotLastEmptyPagePos" varLen="0" name="Envelope lot last blank page position" entity="template" id="TEEnvLotLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeLotLastEmptySheetPos" varLen="0" name="Envelope lot last blank sheet position" entity="template" id="TEEnvLotLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstEmptyPagePos" varLen="0" name="Lot first blank page position" entity="template" id="TELotFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstEmptySheetPos" varLen="0" name="Lot first blank sheet position" entity="template" id="TELotFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotLastEmptyPagePos" varLen="0" name="Lot last blank page position" entity="template" id="TELotLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotLastEmptySheetPos" varLen="0" name="Lot last blank sheet position" entity="template" id="TELotLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstEmptyPagePos" varLen="0" name="Spoolset first blank page position" entity="template" id="TESpoolsetFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstEmptySheetPos" varLen="0" name="Spoolset first blank sheet position" entity="template" id="TESpoolsetFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetLastEmptyPagePos" varLen="0" name="Spoolset last blank page position" entity="template" id="TESpoolsetLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetLastEmptySheetPos" varLen="0" name="Spoolset last blank sheet position" entity="template" id="TESpoolsetLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstEmptyPagePos" varLen="0" name="Spoolfile first blank page position" entity="template" id="TESpoolfileFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstEmptySheetPos" varLen="0" name="Spoolfile first blank sheet position" entity="template" id="TESpoolfileFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileLastEmptyPagePos" varLen="0" name="Spoolfile last blank page position" entity="template" id="TESpoolfileLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileLastEmptySheetPos" varLen="0" name="Spoolfile last blank sheet position" entity="template" id="TESpoolfileLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LastPageisFill" varLen="0" name="Last page is blank" entity="template" id="TELastPageisEmpty" available="post" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedPages" varLen="0" name="Document total personalized pages" entity="template" id="TETotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedPagesNoFill" varLen="0" name="Document total personalized pages without blanks" entity="template" id="TETotalPersonalizedPagesNoFill" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedSheets" varLen="0" name="Document total personalized sheets" entity="template" id="TETotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedSheetsNoFill" varLen="0" name="Document total personalized sheets without blanks" entity="template" id="TETotalPersonalizedSheetsNoFill" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPageSections" name="Document total page sections" varLen="0" entity="template" id="TETotalPageSections" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PageSectionsCounter" name="Page sections counter" varLen="0" entity="template" id="TEPageSectionsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CurrentPersonalizedPage" varLen="0" name="Document current personalized page" entity="template" id="TECurrentPersonalizedPage" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CurrentSheet" varLen="0" name="Document current sheet" entity="template" id="TECurrentSheet" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotId" varLen="50" name="Lot identifier" entity="envelope" id="ENLotId" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetId" varLen="50" name="Spoolset identifier" entity="envelope" id="ENSpoolsetId" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentPos" varLen="0" name="Shipment position" entity="envelope" id="ENDocumentPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentFirstPagePos" varLen="0" name="Shipment first page position" entity="envelope" id="ENDocumentFirstPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentFirstSheetPos" varLen="0" name="Shipment first sheet position" entity="envelope" id="ENDocumentFirstSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentLastPagePos" varLen="0" name="Shipment last page position" entity="envelope" id="ENDocumentLastPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentLastSheetPos" varLen="0" name="Shipment last sheet position" entity="envelope" id="ENDocumentLastSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstPagePos" varLen="0" name="Lot first page position" entity="envelope" id="ENLotFirstPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstSheetPos" varLen="0" name="Lot first sheet position" entity="envelope" id="ENLotFirstSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotLastPagePos" varLen="0" name="Lot last page position" entity="envelope" id="ENLotLastPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotLastSheetPos" varLen="0" name="Lot last sheet position" entity="envelope" id="ENLotLastSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstPagePos" varLen="0" name="Spoolset first page position" entity="envelope" id="ENSpoolsetFirstPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstSheetPos" varLen="0" name="Spoolset first sheet position" entity="envelope" id="ENSpoolsetFirstSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetLastPagePos" varLen="0" name="Spoolset last page position" entity="envelope" id="ENSpoolsetLastPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetLastSheetPos" varLen="0" name="Spoolset last sheet position" entity="envelope" id="ENSpoolsetLastSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstPagePos" varLen="0" name="Spoolfile first page position" entity="envelope" id="ENSpoolfileFirstPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstSheetPos" varLen="0" name="Spoolfile first sheet position" entity="envelope" id="ENSpoolfileFirstSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileLastPagePos" varLen="0" name="Spoolfile last page position" entity="envelope" id="ENSpoolfileLastPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileLastSheetPos" varLen="0" name="Spoolfile last sheet position" entity="envelope" id="ENSpoolfileLastSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedPages" varLen="0" name="Total personalized pages" entity="envelope" id="ENTotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedSheets" varLen="0" name="Total personalized sheets" entity="envelope" id="ENTotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFillPages" varLen="0" name="Total blank pages" entity="envelope" id="ENTotalFillPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalFillSheets" varLen="0" name="Total blank sheets" entity="envelope" id="ENTotalFillSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalCoverPages" varLen="0" name="Total cover pages" entity="envelope" id="ENTotalCoverPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalCoverSheets" varLen="0" name="Total cover sheets" entity="envelope" id="ENTotalCoverSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalExtraPages" varLen="0" name="Total extra pages" entity="envelope" id="ENTotalExtraPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalExtraSheets" varLen="0" name="Total extra sheets" entity="envelope" id="ENTotalExtraSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="envelope" id="ENPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="envelope" id="ENSheetsCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="envelope" id="ENPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="envelope" id="ENSheetsCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="envelope" id="ENPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="envelope" id="ENSheetsCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="envelope" id="ENPagesCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="envelope" id="ENSheetsCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="envelope" id="ENPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="envelope" id="ENPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="envelope" id="ENFillPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="envelope" id="ENFillSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="envelope" id="ENCoverPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="envelope" id="ENCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverExtraPages" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra pages" entity="envelope" id="ENTotalPersCoverExtraPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverExtraSheets" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra sheets" entity="envelope" id="ENTotalPersCoverExtraSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverPages" varLen="0" name="Total personalized&amp;amp;cover pages" entity="envelope" id="ENTotalPersCoverPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedCoverSheets" varLen="0" name="Total personalized&amp;amp;cover sheets" entity="envelope" id="ENTotalPersCoverSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="envelope" id="ENPersCoverExtraPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="envelope" id="ENPersCoverExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;cover pages counter" entity="envelope" id="ENPersCoverPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;cover sheets counter" entity="envelope" id="ENPersCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="envelope" id="ENExtraPagesCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="envelope" id="ENExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileSegmentCounter" varLen="0" name="Envelope spoolfiles counter" entity="envelope" id="ENSegmentCounter" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert1" varLen="0" name="Total sheets insert 1" entity="envelope" id="ENTotalSheets_Insert1" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert2" varLen="0" name="Total sheets insert 2" entity="envelope" id="ENTotalSheets_Insert2" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert3" varLen="0" name="Total sheets insert 3" entity="envelope" id="ENTotalSheets_Insert3" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalSheets_Insert4" varLen="0" name="Total sheets insert 4" entity="envelope" id="ENTotalSheets_Insert4" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Name" name="Name" varLen="256" entity="section" id="PSName" available="pre" createInstance="none" type="string"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPages" name="Total Pages" varLen="0" entity="section" id="PSTotalPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplateFirstPagePos" name="Document first page position" varLen="0" entity="section" id="PSTemplateFirstPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TemplateLastPagePos" name="Document last page position" varLen="0" entity="section" id="PSTemplateLastPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentFirstPagePos" name="Shipment first page position" varLen="0" entity="section" id="PSDocumentFirstPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentLastPagePos" name="Shipment last page position" varLen="0" entity="section" id="PSDocumentLastPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeFirstPagePos" name="Envelope first page position" varLen="0" entity="section" id="PSEnvelopeFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeFirstSheetPos" name="Envelope first sheet position" varLen="0" entity="section" id="PSEnvelopeFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstPagePos" name="Lot first page position" varLen="0" entity="section" id="PSLotFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotFirstSheetPos" name="Lot first sheet position" varLen="0" entity="section" id="PSLotFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstPagePos" name="Spoolset first page position" varLen="0" entity="section" id="PSSpoolsetFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetFirstSheetPos" name="Spoolset first sheet position" varLen="0" entity="section" id="PSSpoolsetFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstPagePos" name="Spoolfile first page position" varLen="0" entity="section" id="PSSpoolfileFirstPagePos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileFirstSheetPos" name="Spoolfile first sheet position" varLen="0" entity="section" id="PSSpoolfileFirstSheetPos" available="post" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedPages" name="Total personalized pages" varLen="0" entity="section" id="PSTotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedPagesNoFill" name="Document total personalized pages without blanks" varLen="0" entity="section" id="PSTotalPersonalizedPagesNoFill" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedSheets" name="Document total personalized sheets" varLen="0" entity="section" id="PSTotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="TotalPersonalizedSheetsNoFill" name="Document total personalized sheets without blanks" varLen="0" entity="section" id="PSTotalPersonalizedSheetsNoFill" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
      &lt;omsf:field varName="EnvelopeLastPagePos" varLen="0" name="Envelope last page position" entity="section" id="PSEnvelopeLastPagePos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="EnvelopeLastSheetPos" varLen="0" name="Envelope last sheet position" entity="section" id="PSEnvelopeLastSheetPos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="EnvelopeLotLastPagePos" varLen="0" name="Envelope lot last page position" entity="section" id="PSEnvLotLastPagePos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="EnvelopeLotLastSheetPos" varLen="0" name="Envelope lot last sheet position" entity="section" id="PSEnvLotLastSheetPos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="SpoolsetLastPagePos" varLen="0" name="Spoolset last page position" entity="section" id="PSSpoolsetLastPagePos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="SpoolsetLastSheetPos" varLen="0" name="Spoolset last sheet position" entity="section" id="PSSpoolsetLastSheetPos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="SpoolfileLastPagePos" varLen="0" name="Spoolfile last page position" entity="section" id="PSSpoolfileLastPagePos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="SpoolfileLastSheetPos" varLen="0" name="Spoolfile last sheet position" entity="section" id="PSSpoolfileLastSheetPos" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="section" id="PSJPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="section" id="PSPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="section" id="PSFillPagesCounter" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="section" id="PSFillSheetsCounter" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="section" id="PSPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="section" id="PSPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="section" id="PSPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;
        &lt;omsf:description/&gt;
      &lt;/omsf:field&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isFront" varLen="0" name="is Front" entity="page" id="PGisFront" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isBack" varLen="0" name="is Back" entity="page" id="PGisBack" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isFill" varLen="0" name="is Blank" entity="page" id="PGisFill" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isCover" varLen="0" name="is Cover" entity="page" id="PGisCover" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isPAGETAG1" varLen="0" name="has page attribute 1" entity="page" id="PGisPAGETAG1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isPAGETAG2" varLen="0" name="has page attribute 2" entity="page" id="PGisPAGETAG2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isPAGETAG3" varLen="0" name="has page attribute 3" entity="page" id="PGisPAGETAG3" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="isPAGETAG4" varLen="0" name="has page attribute 4" entity="page" id="PGisPAGETAG4" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotPagePos" varLen="0" name="Lot page position" entity="page" id="PGLotPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="LotSheetPos" varLen="0" name="Lot sheet position" entity="page" id="PGLotSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopePagePos" varLen="0" name="Envelope page position" entity="page" id="PGEnvelopePagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeSheetPos" varLen="0" name="Envelope sheet position" entity="page" id="PGEnvelopeSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentPagePos" varLen="0" name="Shipment page position" entity="page" id="PGDocumentPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="DocumentSheetPos" varLen="0" name="Shipment sheet position" entity="page" id="PGDocumentSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfilePagePos" varLen="0" name="Spoolfile page position" entity="page" id="PGSpoolfilePagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolfileSheetPos" varLen="0" name="Spoolfile sheet position" entity="page" id="PGSpoolfileSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetPagePos" varLen="0" name="Spoolset page position" entity="page" id="PGSpoolsetPagePos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="SpoolsetSheetPos" varLen="0" name="Spoolset sheet position" entity="page" id="PGSpoolsetSheetPos" available="pre" createInstance="none" type="number"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsFirstPage" varLen="0" name="Is first page of envelope" entity="page" id="PGEnvelopeIsFirstPage" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsFirstSheet" varLen="0" name="Is first sheet of envelope" entity="page" id="PGEnvelopeIsFirstSheet" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsNotFirstPage" varLen="0" name="Is not first page of envelope" entity="page" id="PGEnvelopeIsNotFirstPage" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsNotFirstSheet" varLen="0" name="Is not first sheet of envelope" entity="page" id="PGEnvelopeIsNotFirstSheet" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsLastPage" varLen="0" name="Is last page of envelope" entity="page" id="PGEnvelopeIsLastPage" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsLastSheet" varLen="0" name="Is last sheet of envelope" entity="page" id="PGEnvelopeIsLastSheet" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsNotLastPage" varLen="0" name="Is not last page of envelope" entity="page" id="PGEnvelopeIsNotLastPage" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="EnvelopeIsNotLastSheet" varLen="0" name="Is not last sheet of envelope" entity="page" id="PGEnvelopeIsNotLastSheet" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr3BitsGroupNumberBit0" varLen="0" name="MailSystem envelope counter (3 bits) bit 0" entity="page" id="PGOmr3BitsGroupNumberBit0" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr3BitsGroupNumberBit1" varLen="0" name="MailSystem envelope counter (3 bits) bit 1" entity="page" id="PGOmr3BitsGroupNumberBit1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr3BitsGroupNumberBit2" varLen="0" name="MailSystem envelope counter (3 bits) bit 2" entity="page" id="PGOmr3BitsGroupNumberBit2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsGroupNumberBit0" varLen="0" name="MailSystem envelope counter (4 bits) bit 0" entity="page" id="PGOmr4BitsGroupNumberBit0" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsGroupNumberBit1" varLen="0" name="MailSystem envelope counter (4 bits) bit 1" entity="page" id="PGOmr4BitsGroupNumberBit1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsGroupNumberBit2" varLen="0" name="MailSystem envelope counter (4 bits) bit 2" entity="page" id="PGOmr4BitsGroupNumberBit2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsGroupNumberBit3" varLen="0" name="MailSystem envelope counter (4 bits) bit 3" entity="page" id="PGOmr4BitsGroupNumberBit3" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsGroupNumberBit0" varLen="0" name="MailSystem envelope counter (5 bits) bit 0" entity="page" id="PGOmr5BitsGroupNumberBit0" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsGroupNumberBit1" varLen="0" name="MailSystem envelope counter (5 bits) bit 1" entity="page" id="PGOmr5BitsGroupNumberBit1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsGroupNumberBit2" varLen="0" name="MailSystem envelope counter (5 bits) bit 2" entity="page" id="PGOmr5BitsGroupNumberBit2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsGroupNumberBit3" varLen="0" name="MailSystem envelope counter (5 bits) bit 3" entity="page" id="PGOmr5BitsGroupNumberBit3" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsGroupNumberBit4" varLen="0" name="MailSystem envelope counter (5 bits) bit 4" entity="page" id="PGOmr5BitsGroupNumberBit4" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr3BitsSequenceNumberBit0" varLen="0" name="MailSystem sheet counter (3 bits) bit 0" entity="page" id="PGOmr3BitsSequenceNumberBit0" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr3BitsSequenceNumberBit1" varLen="0" name="MailSystem sheet counter (3 bits) bit 1" entity="page" id="PGOmr3BitsSequenceNumberBit1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr3BitsSequenceNumberBit2" varLen="0" name="MailSystem sheet counter (3 bits) bit 2" entity="page" id="PGOmr3BitsSequenceNumberBit2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsSequenceNumberBit0" varLen="0" name="MailSystem sheet counter (4 bits) bit 0" entity="page" id="PGOmr4BitsSequenceNumberBit0" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsSequenceNumberBit1" varLen="0" name="MailSystem sheet counter (4 bits) bit 1" entity="page" id="PGOmr4BitsSequenceNumberBit1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsSequenceNumberBit2" varLen="0" name="MailSystem sheet counter (4 bits) bit 2" entity="page" id="PGOmr4BitsSequenceNumberBit2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr4BitsSequenceNumberBit3" varLen="0" name="MailSystem sheet counter (4 bits) bit 3" entity="page" id="PGOmr4BitsSequenceNumberBit3" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsSequenceNumberBit0" varLen="0" name="MailSystem sheet counter (5 bits) bit 0" entity="page" id="PGOmr5BitsSequenceNumberBit0" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsSequenceNumberBit1" varLen="0" name="MailSystem sheet counter (5 bits) bit 1" entity="page" id="PGOmr5BitsSequenceNumberBit1" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsSequenceNumberBit2" varLen="0" name="MailSystem sheet counter (5 bits) bit 2" entity="page" id="PGOmr5BitsSequenceNumberBit2" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsSequenceNumberBit3" varLen="0" name="MailSystem sheet counter (5 bits) bit 3" entity="page" id="PGOmr5BitsSequenceNumberBit3" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="Omr5BitsSequenceNumberBit4" varLen="0" name="MailSystem sheet counter (5 bits) bit 4" entity="page" id="PGOmr5BitsSequenceNumberBit4" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IsHeader" varLen="0" name="Is the header page" entity="page" id="PGIsHeader" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
    &lt;omsf:field varName="IsTrailer" varLen="0" name="Is the trailer page" entity="page" id="PGIsTrailer" available="pre" createInstance="none" type="boolean"&gt;
      &lt;omsf:description/&gt;
    &lt;/omsf:field&gt;
  &lt;/omsf:fieldsConfig&gt;`&lt;buildconfig previewTarget="DEFAULT" version="2.7.0"&gt;

**Sample Output Configuration XML File**

&lt;generalConfiguration rendererType="embedded"&gt;

&lt;postProcessing enablePostProcessing="true" pageDatasectionName="" spoolInputFilename="" pagePositionInInputFile="" isFill="" inputPageAttribute1="" inputPageAttribute2="" inputPageAttribute3="" inputPageAttribute4="" inputType="AFPDS" enableExternalPages="false" externalPagesDatasectionName="" pagesRotation="none"&gt;

&lt;advancedSettings&gt;

&lt;advancedSetting outputFormat="AFPDS"/&gt;

&lt;advancedSetting outputFormat="MMD"/&gt;

&lt;advancedSetting outputFormat="FORMDEF"/&gt;

&lt;advancedSetting outputFormat="NAS"/&gt;

&lt;advancedSetting outputFormat="PDF"/&gt;

&lt;/advancedSettings&gt;

&lt;/postProcessing&gt;

&lt;/generalConfiguration&gt;

&lt;targets shapesGeneration="blocks" spacingCompat0="true"&gt;

&lt;target name="DEFAULT" id="DEFAULT" scriptResolution="300" scriptColorModel="cmyk" bwAreaSolid="false" imagesDestinationResolution="300" colorImagesDestinationFormat="jpg" monochromeImagesDestinationFormat="tif" jpegQuality=" 0" codepage="Cp1252" country="IT" compressColorTIFF="true" spoolFormatAfp="true" spoolFormatPdf="true" spoolFormatRaster=" false" spoolFormatPcl="false" spoolFormatPs="false" spoolFormatExcel="false" spoolFormatEmail="false" spoolFormatHtml="

false" spoolFormatInteractiveCommunication="false" includePdfAction="convert" fitToPage="false" allTextToBlack="false" forceExtImageResolution="false" gsubst="replace" spoolFormatCsv="false"&gt;

&lt;fonts&gt;

&lt;family name="Arial" font-family=""&gt;

&lt;bolditalic embed="true" filename="arialbi.ttf"&gt;

&lt;codepages&gt;

&lt;codepage encoding="Cp1252"/&gt;

&lt;/codepages&gt;

&lt;/bolditalic&gt;

&lt;italic embed="true" filename="ariali.ttf"&gt;

&lt;codepages&gt;

&lt;codepage encoding="Cp1252"/&gt;

&lt;/codepages&gt;

&lt;/italic&gt;

&lt;bold embed="false" filename="arialbd.ttf"&gt;

&lt;codepages&gt;

&lt;codepage encoding="Cp1252"/&gt;

&lt;/codepages&gt;

&lt;/bold&gt;

&lt;normal embed="true" filename="arial.ttf"&gt;

&lt;codepages&gt;

&lt;codepage encoding="Cp1252"/&gt;

&lt;/codepages&gt;

&lt;/normal&gt;

&lt;/family&gt;

&lt;/fonts&gt;

&lt;description/&gt;

&lt;PRESoptFile&gt;VGhlc2UgYXJlIG9ubHkgdGhlIG9wdGlvbnMgd2hpY2ggYXJlIGRpZmZlcmVudCBmcm9tIHRoZSBn bG9iYWwgTVBQIG9wdGlvbnMuDUFGUERTX0Nscj0xMA1BRlBEU19FcHNDb250YWluZXI9ZmFsc2UN QUZQRFNfRlM0NT10cnVlDUFGUERTX0pwZWdDb250YWluZXI9ZmFsc2UNQUZQRFNfTWF4VHJheU1h

cHBpbmc9MTANQUZQRFNfUGRmQ29udGFpbmVyPWZhbHNlDUFGUERTX1Jlc291cmNlRGlyPQ1BRlBE U19SZXNvdXJjZU1hbmFnZW1lbnQ9MA1BRlBEU19UaWZmQ29udGFpbmVyPWZhbHNlDURTX0FsbG93 QXBwZW5kVG9PcGVuU3Bvb2w9ZmFsc2UNRFNfQWxsb3dVVEY4SW5wdXQ9dHJ1ZQ1EU19Gb250UGF0 aD0NRFNfR3JhcGhpY1BhdGg9DURTX1BESVBhdGg9DURTX1BSZVNDb21wYXRpYmlsaXR5TW9kZT1m

YWxzZQ1EU19QcmludFN0cmVhbUJ1ZmZlclNpemU9NjU1MzYNRFNfU3RhdHVzRmx1c2hPbldyaXRl PWZhbHNlDURTX1N1cHByZXNzRXh0ZW5zaW9uPWZhbHNlDURTX1N5c3RlbVBhdGg9DURTX1RSRlBh

dGg9DUlKUERTX0NhdE9uZUZvbnRzPWZhbHNlDUlKUERTX0Nscl8wPTANSUpQRFNfQ29tcHJlc3Np b249ZmFsc2UNSUpQRFNfQ3VyQ2ZnPVVubmFtZWQgQ29uZmlndXJhdGlvbg1JSlBEU19EcGx4U2lk ZV8wPTANSUpQRFNfRHJhcGVfMD0wDUlKUERTX0Z1bGxDb2xvdXI9ZmFsc2UNSUpQRFNfTG9va1Vw VGFibGU9DUlKUERTX051bURyb3BzXzBfMD0yDUlKUERTX051bUhlYWRzXzA9MQ1JSlBEU19OdW1K ZXRzXzBfMD0yNjg4DUlKUERTX051bVJpcHM9MQ1JSlBEU19PZmZzZXRfMD0wDUlKUERTX1JlbEhl YWRQb3NfMF8wPTANSUpQRFNfUmVxUmlwcz0xMjgNSUpQRFNfUmVzWF8wPTMwMA1JSlBEU19SZXNZ XzA9MzAwDUlKUERTX1JpcE5hbWVfMD0NSUpQRFNfU09QQnJrUG9zPTANSVBEU19Db21wYXRpYmls aXR5PWZhbHNlDUlQRFNfRk09MA1JUERTX0ZTMTE9ZmFsc2UNSVBEU19GUzQ1PWZhbHNlDUlQRFNf SU09ZmFsc2UNSVBEU19JT0NvbXA9Mg1JUERTX09GPWZhbHNlDVBDTF9DbHI9OQ1QREZfTG9hZEFz VmVjdG9yPXRydWUNUERGX09JQ29uZGl0aW9uPQ1QREZfT0lJQ0NQcm9maWxlRmlsZT0NUERGX09J SW5mbz0NUERGX1N0YW5kYXJkPTANUERGX1ZlY3RvclBhZ2VUaHJlc2hvbGQ9MA1QTUdSX0lEQWRk

cmVzcz0xMjcuMC4wLjENUE1HUl9Qb3J0PTg1MTYNUE1HUl9RdWV1ZT1EZWZhdWx0DVBTQmluTWFw cGluZ3NMaXN0PQ1QU1RyYXlNYXBwaW5nc0xpc3Q9DVJhc3Rlcl9BcHBlbmRUb0ZpbGU9ZmFsc2UN UmFzdGVyX0pQR0F1dG9OdW09ZmFsc2UNUmFzdGVyX0pQR1N0YXJ0VmFsPTENUmFzdGVyX01vbm9j aHJvbWU9ZmFsc2UNUmFzdGVyX091dHB1dD1USUZGDVZEWF9CaW5hcnk9dHJ1ZQ1WRFhfQ29tcHJl c3M9dHJ1ZQ1WRFhfVHJheU1hcHBpbmdMaXN0PQ1WSVBQX0NvbnZlcnRUb1RpZmY9dHJ1ZQ0=&lt;/PRESoptFile&gt;

&lt;colorMaps&gt;

&lt;colorMap enabled="true" RGBHexCode="0x6A1DC" Cvalue="75" Mvalue="20" Yvalue="0" Kvalue="0"/&gt;

&lt;colorMap enabled="true" RGBHexCode="0x9FC9EB" Cvalue="35" Mvalue="10" Yvalue="0" Kvalue="0"/&gt;

&lt;colorMap enabled="true" RGBHexCode="0xD2EDF3" Cvalue="16" Mvalue="0" Yvalue="3" Kvalue="0"/&gt;

&lt;colorMap enabled="true" RGBHexCode="0xEEF8F6" Cvalue="5" Mvalue="0" Yvalue="3" Kvalue="0"/&gt;

&lt;/colorMaps&gt;

&lt;PPDFile originalFileName="" imageCaching=""/&gt;

&lt;PclSettings&gt;

&lt;PclSetting enable="false" enableOffset="true" horizOffset="25400" vertOffset="50800" headerConstantCommand="" horizOffsetBack="25400" vertOffsetBack="50800" incrementWidth="false"/&gt;

&lt;/PclSettings&gt;

&lt;PdfSettings&gt;

&lt;PdfSetting enable="false" profile="pdf" optimizeThinLines="false" thinLinesOptimizationThreshold="106" singleByteEncoding="false" deepPagesTree="false"/&gt;

&lt;/PdfSettings&gt;

&lt;AFPSettings useFormDef="true" forceMonoImages="false" forceBW="false" allowWhiteTextOnBW="false" useEBCDIC="false" G4compression="false" colorImagesFormat="jpeg"/&gt;

&lt;ExcelSettings isXls="false" isXlsx="false"/&gt;

&lt;EmailSettings body="1"/&gt;

&lt;RasterSettings type="tiff" transparentBackground="true" highQuality="true" compression="rle"/&gt;

&lt;EipaSettings eipaDocumentName=""&gt;

&lt;attachment enable="false" includeAtt="false" sourceAtt=""&gt;

&lt;internalAttachment enable="false" description=""/&gt;

&lt;externalAttachment enable="false" description="" name="" format="" compression=""/&gt;

&lt;/attachment&gt;

&lt;/EipaSettings&gt;

&lt;CsvSettings separator="semicolon"/&gt;

&lt;IFSettings discardTransactionalData="false" storeImages="false"/&gt;

&lt;ICSettings ttsCaching="true"/&gt;

&lt;/target&gt;

&lt;/targets&gt;

&lt;serializers&gt;

&lt;serializer name="DEFAULT" id="DEFAULT" codePage="Cp1252" countPersonalizedBlanksAsPers="false"&gt;

&lt;description/&gt;

&lt;customFields&gt;

&lt;printjobFields&gt;

&lt;field id="LOT_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;REVGQVVMVA==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="SEMAPHORE_BASE_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="PJJobId" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Xw==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRINT_FILE_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="SSSpoolfilesCounter" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Lg==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJSpoolfileExtension" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRINT_SME_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LnNtZQ==&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_BASE_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="/FILE/DOCUMENT/@code" dataProvider="document"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Xw==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="SSEnvelopesCounter" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_SPOOL_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="EMAIL_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Lg==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJSpoolfileExtension" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_LOTXML_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LmxvdHhtbA==&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_SEMAPHORE_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LnNtZQ==&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_BODY_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="EMAIL_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Lmh0bWw=&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_LOTXML_HEADER" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="5000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NPGxvdCB4bWxucz0iaHR0cDov L2VkZWxpdmVyeS5lYmlsbGluZy5pdC9zY2hlbWEvbG90Ij4NPGV4dGVybmFsSWQ+MTwvZXh0ZXJu YWxJZD4NPGRlc2NyaXB0aW9uPkJsdWVCYW5rIERlbW88L2Rlc2NyaXB0aW9uPg08cHJpb3JpdHk+ Tk9STUFMPC9wcmlvcml0eT4NPG1lc3NhZ2VzPg==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_LOTXML_FOOT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="1000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PC9tZXNzYWdlcz4NPHByb3BlcnRpZXM+DTxwcm9wZXJ0eSBuYW1lPSJMT1RfRVhURVJOQUxfSUQi Pg08dmFsdWU+JExPVElEPC92YWx1ZT4NPC9wcm9wZXJ0eT4NPHByb3BlcnR5IG5hbWU9IklEX1BS

T0pFQ1QiPg08dmFsdWU+NTIyNDwvdmFsdWU+DTwvcHJvcGVydHk+DTxwcm9wZXJ0eSBuYW1lPSJM T1RfUFJJT1JJVFkiPg08dmFsdWU+Tk9STUFMPC92YWx1ZT4NPC9wcm9wZXJ0eT4NPHByb3BlcnR5 IG5hbWU9IkxPVF9OT1RJRllfUkVDSVBJRU5UX1RPIj4NPHZhbHVlPiRMT1RfTk9USUZZX1JFQ0lQ

SUVOVF9UTzwvdmFsdWU+DTwvcHJvcGVydHk+DTxwcm9wZXJ0eSBuYW1lPSJMT1RfTk9USUZZX1JF Q0lQSUVOVF9DQyI+DTx2YWx1ZT4kTE9UX05PVElGWV9SRUNJUElFTlRfQ0M8L3ZhbHVlPg08L3By

b3BlcnR5Pg08cHJvcGVydHkgbmFtZT0iTE9UX05PVElGWV9SRUNJUElFTlRfQkNDIj4NPHZhbHVl PiRMT1RfTk9USUZZX1JFQ0lQSUVOVF9CQ0M8L3ZhbHVlPg08L3Byb3BlcnR5Pg08cHJvcGVydHkg bmFtZT0iTE9UX05PVElGWV9GUk9NIj4NPHZhbHVlPiRMT1RfTk9USUZZX0ZST008L3ZhbHVlPg08

L3Byb3BlcnR5Pg08cHJvcGVydHkgbmFtZT0iTE9UX05PVElGWV9SRVBMWVRPIj4NPHZhbHVlPiRM T1RfTk9USUZZX1JFUExZVE88L3ZhbHVlPg08L3Byb3BlcnR5Pg08cHJvcGVydHkgbmFtZT0iTE9U X05PVElGWV9QUklPUklUWSI+DTx2YWx1ZT4kTE9UX05PVElGWV9QUklPUklUWTwvdmFsdWU+DTwv

cHJvcGVydHk+DTwvcHJvcGVydGllcz4NPGZyb21EYXRlPjIwMDAtMDEtMDE8L2Zyb21EYXRlPg08 ZXhwaXJ5RGF0ZT4yMDIwLTEyLTMxPC9leHBpcnlEYXRlPg08L2xvdD4=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_LOTXML_BODY" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="5000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PG1lc3NhZ2U+DTxnYXRld2F5cz4NPGdhdGV3YXk+DTxlbWFpbD4NPGNvZGVwYWdlPlVURi04PC9j b2RlcGFnZT4NPHN1YmplY3Q+Qmx1ZUJhbmsgU3RhdGVtZW50ICMkSU5WT0lDRV9JRDwvc3ViamVj dD4NPHJlY2lwaWVudHM+DTxyZWNpcGllbnQ+DTxhZGRyZXNzPiREU1RfRU1BSUw8L2FkZHJlc3M+ DTxuYW1lPiREU1RfTkFNRTwvbmFtZT4NPHR5cGU+VE88L3R5cGU+DTwvcmVjaXBpZW50Pg08L3Jl

Y2lwaWVudHM+DTxib2R5Pg08aHRtbD4NPHBhdGg+JEJPRFlfUEFUSDwvcGF0aD4NPC9odG1sPg08 L2JvZHk+DTxhdHRhY2htZW50cz4NPGh5cGVybGluaz4NPGZpbGU+DTxwbGFjZWhvbGRlcj5bc3Rh dGVtZW50XTwvcGxhY2Vob2xkZXI+DTxwYXRoPiRBVFRBQ0hNRU5UX1BBVEg8L3BhdGg+DTwvZmls ZT4NPC9oeXBlcmxpbms+DTwvYXR0YWNobWVudHM+DTxmcm9tPg08YWRkcmVzcz5ibHVlYmFua0Bk b3hlZS5jb208L2FkZHJlc3M+DTxuYW1lPkRveGVlIEJsdWVCYW5rPC9uYW1lPg08L2Zyb20+DTxw cmlvcml0eT5OT1JNQUw8L3ByaW9yaXR5Pg08ZGVsaXZlcnlTdGF0dXNOb3RpZmljYXRpb25zPmZh bHNlPC9kZWxpdmVyeVN0YXR1c05vdGlmaWNhdGlvbnM+DTxtZXNzYWdlRGlzcG9zaXRpb25Ob3Rp

ZmljYXRpb25zPmZhbHNlPC9tZXNzYWdlRGlzcG9zaXRpb25Ob3RpZmljYXRpb25zPg08L2VtYWls Pg08L2dhdGV3YXk+DTwvZ2F0ZXdheXM+DTwvbWVzc2FnZT4=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_LOTXML_BODY_RE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="5000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JElOVk9JQ0VfSUQ=&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PRX_INVOICE_ID" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JERTVF9FTUFJTA==&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PRX_DST_EMAIL" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JERTVF9OQU1F&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PRX_CUSTOMER_NAME" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JEJPRFlfUEFUSA==&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="EMAIL_BODY_NAME" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JEFUVEFDSE1FTlRfUEFUSA==&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="EMAIL_SPOOL_NAME" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="EMAIL_LOTXML_BODY" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRX_INVOICE_ID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/@code" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRX_CUSTOMER_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="210" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@fullName" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRX_DST_EMAIL" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="250" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@email" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_BODY_CONT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="12000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PGh0bWw+DTxoZWFkPg08dGl0bGU+Qmx1ZUJhbmsgU3RhdGVtZW50IGVtYWlsIG1lc3NhZ2U8L3Rp dGxlPg08c3R5bGUgdHlwZT0idGV4dC9jc3MiPg1ib2R5IHsNbWFyZ2luOjA7DXBhZGRpbmc6MDsN fQ0NI2xvZ29iYW5uZXIgew13aWR0aDoxMDAlOw19DQ0jbG9nbyB7DXBvc2l0aW9uOmFic29sdXRl Ow1sZWZ0OjIwcHg7DW1hcmdpbi10b3A6M3B4Ow19DQ0jYmFubmVyIHsNd2lkdGg6MTAwJTsNaGVp Z2h0OjU1cHg7DW1hcmdpbjowOw1iYWNrZ3JvdW5kOiAjMDZhMWRjOyAvKiBPbGQgYnJvd3NlcnMg Ki8NYmFja2dyb3VuZDogLW1vei1saW5lYXItZ3JhZGllbnQobGVmdCwgICMwNmExZGMgMCUsICNl ZWY4ZjYgMTAwJSk7IC8qIEZGMy42KyAqLw1iYWNrZ3JvdW5kOiAtd2Via2l0LWdyYWRpZW50KGxp bmVhciwgbGVmdCB0b3AsIHJpZ2h0IHRvcCwgY29sb3Itc3RvcCgwJSwjMDZhMWRjKSwgY29sb3It c3RvcCgxMDAlLCNlZWY4ZjYpKTsgLyogQ2hyb21lLFNhZmFyaTQrICovDWJhY2tncm91bmQ6IC13 ZWJraXQtbGluZWFyLWdyYWRpZW50KGxlZnQsICAjMDZhMWRjIDAlLCNlZWY4ZjYgMTAwJSk7IC8q IENocm9tZTEwKyxTYWZhcmk1LjErICovDWJhY2tncm91bmQ6IC1vLWxpbmVhci1ncmFkaWVudChs ZWZ0LCAgIzA2YTFkYyAwJSwjZWVmOGY2IDEwMCUpOyAvKiBPcGVyYSAxMS4xMCsgKi8NYmFja2dy b3VuZDogLW1zLWxpbmVhci1ncmFkaWVudChsZWZ0LCAgIzA2YTFkYyAwJSwjZWVmOGY2IDEwMCUp OyAvKiBJRTEwKyAqLw1iYWNrZ3JvdW5kOiBsaW5lYXItZ3JhZGllbnQobGVmdCwgICMwNmExZGMg MCUsI2VlZjhmNiAxMDAlKTsgLyogVzNDICovDWZpbHRlcjogcHJvZ2lkOkRYSW1hZ2VUcmFuc2Zv cm0uTWljcm9zb2Z0LmdyYWRpZW50KCBzdGFydENvbG9yc3RyPScjMDZhMWRjJywgZW5kQ29sb3Jz dHI9JyNlZWY4ZjYnLEdyYWRpZW50VHlwZT0xICk7IC8qIElFNi05ICovDX0NDSNvdXRlckNvbnRl bnQgew13aWR0aDo2MDBweDsNaGVpZ2h0OjE4MHB4Ow1tYXJnaW46YXV0bzsNbWFyZ2luLXRvcDox MHB4Ow1mb250LWZhbWlseTogQXJpYWw7DWZvbnQtc2l6ZTogMTRweDsNfQ0NI2NvbnRlbnQgew13 aWR0aDo2MDBweDsNaGVpZ2h0OjE4MHB4Ow1ib3JkZXI6MXB4IHNvbGlkICMwNmExZGM7DXBhZGRp bmc6MTBweDsNZm9udC1mYW1pbHk6SGVsdmV0aWNhLCBBcmlhbCwgc2Fucy1zZXJpZjsNY29sb3I6 IzA2YTFkYzsNfQ0NLnNpZ25hdHVyZSB7DWZvbnQtc3R5bGU6aXRhbGljOw1jb2xvcjpsaWdodGdy ZXk7DXRleHQtYWxpZ246cmlnaHQ7DXdpZHRoOjEwMCU7DWZvbnQtc2l6ZToxMXB0Ow19DQ0jZGlz Y2xhaW1lciB7DWZvbnQtc3R5bGU6aXRhbGljOw1jb2xvcjpsaWdodGdyZXk7DXRleHQtYWxpZ246 Y2VudGVyOw1mb250LXNpemU6OXB0Ow10b3A6MzAwcHg7DWZvbnQtZmFtaWx5OkhlbHZldGljYSwg QXJpYWwsIHNhbnMtc2VyaWY7DQ0gICAgbWFyZ2luOiBhdXRvOw0gICAgcGFkZGluZy1sZWZ0OiA0 MHB4Ow0gICAgd2lkdGg6IDYyM3B4Ow0NfQ0NI2Zvb3RlciB7DXBvc2l0aW9uOiBhYnNvbHV0ZTsN Ym90dG9tOiAwOw1sZWZ0OiAwOw13aWR0aDoxMDAlOw1oZWlnaHQ6MTBweDsNYmFja2dyb3VuZDog IzA2YTFkYzsgLyogT2xkIGJyb3dzZXJzICovDWJhY2tncm91bmQ6IC1tb3otbGluZWFyLWdyYWRp ZW50KGxlZnQsICAjMDZhMWRjIDAlLCAjZWVmOGY2IDEwMCUpOyAvKiBGRjMuNisgKi8NYmFja2dy b3VuZDogLXdlYmtpdC1ncmFkaWVudChsaW5lYXIsIGxlZnQgdG9wLCByaWdodCB0b3AsIGNvbG9y LXN0b3AoMCUsIzA2YTFkYyksIGNvbG9yLXN0b3AoMTAwJSwjZWVmOGY2KSk7IC8qIENocm9tZSxT YWZhcmk0KyAqLw1iYWNrZ3JvdW5kOiAtd2Via2l0LWxpbmVhci1ncmFkaWVudChsZWZ0LCAgIzA2 YTFkYyAwJSwjZWVmOGY2IDEwMCUpOyAvKiBDaHJvbWUxMCssU2FmYXJpNS4xKyAqLw1iYWNrZ3Jv dW5kOiAtby1saW5lYXItZ3JhZGllbnQobGVmdCwgICMwNmExZGMgMCUsI2VlZjhmNiAxMDAlKTsg LyogT3BlcmEgMTEuMTArICovDWJhY2tncm91bmQ6IC1tcy1saW5lYXItZ3JhZGllbnQobGVmdCwg ICMwNmExZGMgMCUsI2VlZjhmNiAxMDAlKTsgLyogSUUxMCsgKi8NYmFja2dyb3VuZDogbGluZWFy LWdyYWRpZW50KGxlZnQsICAjMDZhMWRjIDAlLCNlZWY4ZjYgMTAwJSk7IC8qIFczQyAqLw1maWx0 ZXI6IHByb2dpZDpEWEltYWdlVHJhbnNmb3JtLk1pY3Jvc29mdC5ncmFkaWVudCggc3RhcnRDb2xv cnN0cj0nIzA2YTFkYycsIGVuZENvbG9yc3RyPScjZWVmOGY2JyxHcmFkaWVudFR5cGU9MSApOyAv KiBJRTYtOSAqLw19DQ0vKiBTaGFyZWQgc3R5bGVzICovDQ0gICAgICAgIC5kcm9wLXNoYWRvdyB7 DSAgICAgICAgICAgIHBvc2l0aW9uOnJlbGF0aXZlOw0gICAgICAgICAgICBmbG9hdDpsZWZ0Ow0g ICAgICAgICAgICB3aWR0aDo0MCU7DSAgICAgICAgICAgIHBhZGRpbmc6MWVtOw0gICAgICAgICAg

ICBtYXJnaW46MmVtIDEwcHggMWVtOw0gICAgICAgICAgICBiYWNrZ3JvdW5kOiNmZmY7DSAgICAg

ICAgICAgIC13ZWJraXQtYm94LXNoYWRvdzowIDFweCA0cHggcmdiYSgwLCAwLCAwLCAwLjMpLCAw IDAgNDBweCByZ2JhKDAsIDAsIDAsIDAuMSkgaW5zZXQ7DSAgICAgICAgICAgICAgIC1tb3otYm94 LXNoYWRvdzowIDFweCA0cHggcmdiYSgwLCAwLCAwLCAwLjMpLCAwIDAgNDBweCByZ2JhKDAsIDAs IDAsIDAuMSkgaW5zZXQ7DSAgICAgICAgICAgICAgICAgICAgYm94LXNoYWRvdzowIDFweCA0cHgg cmdiYSgwLCAwLCAwLCAwLjMpLCAwIDAgNDBweCByZ2JhKDAsIDAsIDAsIDAuMSkgaW5zZXQ7DSAg ICAgICAgfQ0NICAgICAgICAuZHJvcC1zaGFkb3c6YmVmb3JlLA0gICAgICAgIC5kcm9wLXNoYWRv dzphZnRlciB7DSAgICAgICAgICAgIGNvbnRlbnQ6IiI7DSAgICAgICAgICAgIHBvc2l0aW9uOmFi c29sdXRlOw0gICAgICAgICAgICB6LWluZGV4Oi0yOw0gICAgICAgIH0NDS8qIExpZnRlZCBjb3Ju

ZXJzICovDQ0gICAgICAgIC5saWZ0ZWQgew0gICAgICAgICAgICAtbW96LWJvcmRlci1yYWRpdXM6 NHB4Ow0gICAgICAgICAgICAgICAgIGJvcmRlci1yYWRpdXM6NHB4Ow0gICAgICAgIH0NDSAgICAg

ICAgLmxpZnRlZDpiZWZvcmUsDSAgICAgICAgLmxpZnRlZDphZnRlciB7DSAgICAgICAgICAgIGJv dHRvbToxNXB4Ow0gICAgICAgICAgICBsZWZ0OjEwcHg7DSAgICAgICAgICAgIHdpZHRoOjUwJTsN ICAgICAgICAgICAgaGVpZ2h0OjIwJTsNICAgICAgICAgICAgbWF4LXdpZHRoOjMwMHB4Ow0gICAg ICAgICAgICBtYXgtaGVpZ2h0OjEwMHB4Ow0gICAgICAgICAgICAtd2Via2l0LWJveC1zaGFkb3c6 MCAxNXB4IDEwcHggcmdiYSgwLCAwLCAwLCAwLjcpOw0gICAgICAgICAgICAgICAtbW96LWJveC1z aGFkb3c6MCAxNXB4IDEwcHggcmdiYSgwLCAwLCAwLCAwLjcpOw0gICAgICAgICAgICAgICAgICAg IGJveC1zaGFkb3c6MCAxNXB4IDEwcHggcmdiYSgwLCAwLCAwLCAwLjcpOw0gICAgICAgICAgICAt d2Via2l0LXRyYW5zZm9ybTpyb3RhdGUoLTNkZWcpOw0gICAgICAgICAgICAgICAtbW96LXRyYW5z Zm9ybTpyb3RhdGUoLTNkZWcpOw0gICAgICAgICAgICAgICAgLW1zLXRyYW5zZm9ybTpyb3RhdGUo LTNkZWcpOw0gICAgICAgICAgICAgICAgIC1vLXRyYW5zZm9ybTpyb3RhdGUoLTNkZWcpOw0gICAg ICAgICAgICAgICAgICAgIHRyYW5zZm9ybTpyb3RhdGUoLTNkZWcpOw0gICAgICAgIH0NDSAgICAg ICAgLmxpZnRlZDphZnRlciB7DSAgICAgICAgICAgIHJpZ2h0OjEwcHg7DSAgICAgICAgICAgIGxl ZnQ6YXV0bzsNICAgICAgICAgICAgLXdlYmtpdC10cmFuc2Zvcm06cm90YXRlKDNkZWcpOw0gICAg ICAgICAgICAgICAtbW96LXRyYW5zZm9ybTpyb3RhdGUoM2RlZyk7DSAgICAgICAgICAgICAgICAt bXMtdHJhbnNmb3JtOnJvdGF0ZSgzZGVnKTsNICAgICAgICAgICAgICAgICAtby10cmFuc2Zvcm06 cm90YXRlKDNkZWcpOw0gICAgICAgICAgICAgICAgICAgIHRyYW5zZm9ybTpyb3RhdGUoM2RlZyk7 DSAgICAgICAgfQ0NPC9zdHlsZT4NPC9oZWFkPg08Ym9keT4NPGRpdiBpZD0ibG9nb2Jhbm5lciI+ PC9kaXY+DTxkaXYgaWQ9ImxvZ28iPg08aW1nIHNyYz0iaHR0cDovL3VzMS5jbG91ZC5kb3hlZS5j b20vaW1hZ2VzL2JsdWViYW5rL2xvZ28ucG5nIj4NPC9kaXY+DTxkaXYgaWQ9ImJhbm5lciI+PC9k aXY+DTxkaXYgaWQ9Im91dGVyQ29udGVudCI+DTxkaXYgaWQ9ImNvbnRlbnQiIGNsYXNzPSJkcm9w LXNoYWRvdyBsaWZ0ZWQiPg08cCBjbGFzcz0iY1RpdGxlIj4kTkFNRSw8L3A+DTxwPllvdXIgc2F0 ZXRlbWVudCBpcyBhdmFpbGFibGUgb25saW5lITwvcD4NPHA+PGEgaHJlZj0iW3N0YXRlbWVudF0i PkNsaWNrIGhlcmU8L2E+IHRvIHZpZXcgdGhlIHN0YXRlbWVudCBvciB2aXNpdCA8YSBocmVmPSJ3 d3cuYmx1ZWJhbmsuY29tL29ubGluZSI+d3d3LmJsdWViYW5rLmNvbS9vbmxpbmU8L2E+IGFuZCBs b2cgaW4gaW50byB5b3VyIHByaXZhdGUgYXJlYSBhbmQgdmlldyB0aGUgc3RhdGVtZW50IG9ubGlu ZS48L3A+DTxwIGNsYXNzPSJzaWduYXR1cmUiPkJsdWVCYW5rPC9wPg08L2Rpdj4NPC9kaXY+DTxk aXYgaWQ9ImRpc2NsYWltZXIiPg08cD5UaGlzIG1lc3NhZ2Ugd2FzIHNlbnQgdG8gJEVNQUlMIGJ5 IEJsdWVCYW5rPC9icj5CbHVlQmFuayB3aWxsIG5ldmVyIGFzayBmb3IgeW91c2VyIG5hbWUgYW5k IHBhc3N3b3JkLiBJZiB5b3UgdGhpbmsgdGhpcyBtZXNzYWdlIGxvb2tzIHN1c3BpY2lvdXMsIHBs ZWFzZSBjb250YWN0IDU1NSAxMjM0IDU2Nzg8L2JyPkJsdWVCYW5rLCAyMDMzIEdhdGV3YXkgUGxh

Y2UsIFN1aXRlIDUwMCwgOTUxMTAgU2FuIEpvc2UsIENBPC9wPg08L2Rpdj4NPGRpdiBpZD0iZm9v

dGVyIj48L2Rpdj4NPC9ib2R5Pg08L2h0bWw+&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_BODY_CONT_RE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="12000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JE5BTUU=&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PRX_CUSTOMER_NAME" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JEVNQUlM&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PRX_DST_EMAIL" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="EMAIL_BODY_CONT" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DATAMATRIX_VALUE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="72" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="PRX_INVOICE_ID" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PRX_CUSTOMER_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PRX_STATE" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRX_STATE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressStateShort" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="IMB_VALUE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDEyMzQ1NjcwOTQ5ODc2NTQzMjEwMTIzNDU2Nzg5MQ==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550_FILENAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="256" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;const&gt;MDA1NTBfRUxPR0RBVEFfMDAwXw==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LnBhY2thZ2Vy&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560_FILENAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="256" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;const&gt;MDA1NjBfRUxPR0RBVEFfMDAwXw==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LnBhY2thZ2Vy&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_00_RECORDTYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDA=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_02_LOTID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_03_CLIENTID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="EXT_CLIENT_ID" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_04_ACCOUNTID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="EXT_ENV_ID" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_05_JOBID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_06_WORKTYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDE=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_07_WORKSTAGE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDA1NTA=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_08_OWNER" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="EXT_OWNER" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_09_HOSTNAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="20" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;RE9YRUU=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_10_APPTYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;REM=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_11_PROCEDURE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;Qmx1ZUJhbmsgU3RhdGVtZW50&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_12_PROCVERS" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="20" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MQ==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_13_JOBRESULT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="1" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MQ==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_14_AUTOCLOSE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="1" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MA==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_15_CUSTOM01" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_16_CUSTOM02" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_17_CUSTOM03" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_18_CUSTOM04" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550H_19_CUSTOM05" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_00_RECORDTYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDE=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_02_ID_ISTANZA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_03_ID_MISSIVA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="35" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJDocumentsCounter" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_04_ID_LOTTO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_05_NOME_LOTTO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="64" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_06_SIZE_LOTTO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_07_CODICE_P_P" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;QlBPX1VTUFM=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_08_ID_CONTAIN" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_09_NOME_CONTA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="64" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_10_TS_CREAZIO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="14" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTimestamp" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_11_ID_SOURCE_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJePublishCustomField2" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_12_FILENAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="SFFileName" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_13_FILEPATH" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="215" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="SFSpoolfilesAbsPath" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_14_FILE_SIZE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="18" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_15_FILE_TYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_16_ID_PROD" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJJobId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_17_TS_INIZIO_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="14" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTimestamp" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_18_TS_FINE_JO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="14" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTimestamp" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_19_RECORD_STA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DODatafileStartPos" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_20_RECORD_END" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DODatafileStartPos" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_21_PROGRESSIV" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJDocumentsCounter" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_22_PROGRESSIV" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJPersonCoverExtraPagesCounter" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_23_DOCUMENTI" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTotalTemplates" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_24_PAGINE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTotalPersCoverPages" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_25_PAGINE_BIA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTotalFillPages" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_26_FOGLI" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="DOTotalPersCoverExtraSheets" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_27_BOLLETTINI" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MA==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_28_VIA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressLine1" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_29_CAP" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressZipCode" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_30_LOCALITA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="30" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressCity" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_31_PROVINCIA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@addressStateLong" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_32_ANAGRAFICA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_33_ANAGRAFICA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_34_ANAGRAFICA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_35_CODICE_DOC" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJDocumentsCounter" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_36_TIPO_DOCUM" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_37_CANALE_P" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDE=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_38_FORMATO_P" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDE=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_39_EMISSIONE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJJobId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_40_SOCIETA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="20" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_41_DIVISIONE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="20" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_42_MERCATO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="64" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_43_IMPORTO_TO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="21" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_44_CODICE_MOD" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_45_CODICE_COL" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_46_CODICE_DUP" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_47_NUMRACCAND" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="11" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_48_NUMRACCRIT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="11" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_49_BARCODE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="20" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_50_AREA_POSTA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;ZGVmYXVsdA==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_51_PESO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="ENV_TOTAL_WEIGHT" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_52_ALLEGATI_T" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_53_NUM_ALLEGA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="18" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_54_ALLEGATI_T" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_55_NUM_ALLEGA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="18" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_56_ALLEGATI_T" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_57_NUM_ALLEGA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="18" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_58_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_59_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_60_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_61_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_62_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_63_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_64_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_65_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="15" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_66_ID_SUB_PRO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_67_CUSTOM_VC_" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560H_01_ID_JOB" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJJobId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560H_02_ID_LOTTO" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_01_ID_BUSTA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="35" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_02_ID_DOCUMEN" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="35" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_03_CODICE_MOD" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDY=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_04_TIPOLOGIA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_05_ID_ACQUISI" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="15" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_06_DATA_SCADE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="19" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_07_DATA_EMISS" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="19" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MjAxMjA3MjAyMDIwMjA=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_08_CODICE_DOC" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_09_CODICE_DES" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="32" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@customerCode" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_10_NOME_DESTI" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_11_PIVACF_DES" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="16" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_12_IMPORTO_PA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="21" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_13_PESO_DOCUM" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="22" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="ENV_SHEETS_WEIGHT" dataProvider="custom"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_14_PRESENZA_B" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="1" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MA==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_15_CODICE_DOC" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="128" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EXT_ID_CAPTURE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJePublishCustomField2" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EXT_CLIENT_ID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJePublishCustomField3" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EXT_ENV_ID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJePublishCustomField4" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EXT_CHANNEL_ID" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJePublishCustomField1" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EXT_OWNER" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="PJePublishCustomField5" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_07_CODICE_P_E" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;RUJJX0VCSQ==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_37_CANALE_E" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDQ=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_38_FORMATO_E" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDI=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_07_CODICE_P_A" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;RUJJX0VCSQ==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_37_CANALE_A" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDI=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR550D_38_FORMATO_A" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="8" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDI=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560D_00_RECORDTYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="left" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDE=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="TR560H_00_RECORDTYPE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="2" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;MDA=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ENV_TOTAL_WEIGHT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;number approx="none"/&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;math&gt;

&lt;add/&gt;

&lt;/math&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="ENV_SHEETS_WEIGHT" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;NQ==&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ENV_SHEETS_WEIGHT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;number approx="none"/&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;math&gt;

&lt;multiply/&gt;

&lt;/math&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;const&gt;NQ==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="DOTotalPersCoverExtraSheets" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ARCH_SPOOL_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="ARCH_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Lg==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="PJSpoolfileExtension" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ARCH_BASE_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="/FILE/DOCUMENT/@code" dataProvider="document"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;Xw==&lt;/const&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;value fieldRef="SSEnvelopesCounter" dataProvider="system"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="EMAIL_LOTXML_FOOT_RE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="1000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JExPVElE&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="EMAIL_LOTXML_FOOT" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DOCLIST_HEADER" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PGRvY2xpc3Q+PGNyZWF0ZWQ+JHtDUkVBVEVEfTwvY3JlYXRlZD4=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DOCLIST_DOCUMENT" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="300" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PGRvYyBucHJvZz0iMDAwMDAxIiBrMT0iIiBrMj0iIiBrMz0iIiBrND0iIiBrNT0iIiBrNj0iIiBr Nz0iIiBrOD0iIiBrOT0iIiBrMTA9IiIgazExPSIiIGsxMj0iIiBrMTM9IiIgazE0PSIiIGsxNT0i IiBrMTY9IiIgazE3PSIiIGsxOD0iIiBrMTk9IiIgazIwPSIiIHBkZj0iJHtOQU1FfSIgLz4=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DOCLIST_FOOTER" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="20" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PC9kb2NsaXN0Pg==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DOCLIST_FILE_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="50" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;ZXByb29mX2RvY2xpc3QueG1s&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DOCLIST_DOCUMENT_REP" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="300" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JHtOQU1FfQ==&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="ARCH_SPOOL_NAME" dataProvider="custom"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="DOCLIST_DOCUMENT" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="DOCLIST_HEADER_REP" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JHtDUkVBVEVEfQ==&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PJStartTimestamp" dataProvider="system"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="DOCLIST_HEADER" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PROGRESSIVO_BUSTA" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="SFEnvelopesCounter" dataProvider="system"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRINT_LOTXML_BODY" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="5000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NPGxvdCB4bWxucz0iaHR0cDov L2VkZWxpdmVyeS5lYmlsbGluZy5pdC9zY2hlbWEvbG90IiB4bWxuczp4c2k9Imh0dHA6Ly93d3cu dzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIj4NPGV4dGVybmFsSWQ+JExPVElEPC9leHRl cm5hbElkPg08ZGVzY3JpcHRpb24+Qmx1ZUJhbmsgRlRQIDwvZGVzY3JpcHRpb24+DTxwcmlvcml0 eT5ISUdIPC9wcmlvcml0eT4NPG1lc3NhZ2VzPg08bWVzc2FnZT4NPGdhdGV3YXlzPg08Z2F0ZXdh eT4NPGZ0cD4NPGZpbGVzPg08ZmlsZT4NPHBhdGg+cHJpbnQuemlwPC9wYXRoPg08L2ZpbGU+DTwv ZmlsZXM+DTwvZnRwPg08L2dhdGV3YXk+DTwvZ2F0ZXdheXM+DTwvbWVzc2FnZT4NPC9tZXNzYWdl

cz4NPC9sb3Q+&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRINT_LOTXML_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LmxvdHhtbA==&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PRINT_LOTXML_BODY_RE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="1000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JExPVElE&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="PRINT_LOTXML_BODY" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ARCH_LOTXML_BODY" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="5000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4NPGxvdCB4bWxucz0iaHR0cDov L2VkZWxpdmVyeS5lYmlsbGluZy5pdC9zY2hlbWEvbG90IiB4bWxuczp4c2k9Imh0dHA6Ly93d3cu dzMub3JnLzIwMDEvWE1MU2NoZW1hLWluc3RhbmNlIj4NPGV4dGVybmFsSWQ+JExPVElEPC9leHRl cm5hbElkPg08ZGVzY3JpcHRpb24+Qmx1ZUJhbmsgRlRQIDwvZGVzY3JpcHRpb24+DTxwcmlvcml0 eT5ISUdIPC9wcmlvcml0eT4NPG1lc3NhZ2VzPg08bWVzc2FnZT4NPGdhdGV3YXlzPg08Z2F0ZXdh eT4NPGZ0cD4NPGZpbGVzPg08ZmlsZT4NPHBhdGg+YXJjaGl2ZS56aXA8L3BhdGg+DTwvZmlsZT4N PC9maWxlcz4NPC9mdHA+DTwvZ2F0ZXdheT4NPC9nYXRld2F5cz4NPC9tZXNzYWdlPg08L21lc3Nh Z2VzPg08L2xvdD4=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ARCH_LOTXML_BODY_RE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="1000" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;replace&gt;

&lt;replacementToken&gt;

&lt;source&gt;

&lt;const&gt;JExPVElE&lt;/const&gt;

&lt;/source&gt;

&lt;replacement&gt;

&lt;value fieldRef="PJLotId" dataProvider="system"/&gt;

&lt;/replacement&gt;

&lt;/replacementToken&gt;

&lt;/replace&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="ARCH_LOTXML_BODY" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="ARCH_LOTXML_NAME" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="100" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="SEMAPHORE_BASE_NAME" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;operand&gt;

&lt;const&gt;LmxvdHhtbA==&lt;/const&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="OWNER_PW" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;b3duZXI=&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="USER_PW" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;const&gt;dXNlcg==&lt;/const&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PWD_USER_DATAFILE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="USER_1" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="PWD_OWNER_DATAFILE" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;expression&gt;

&lt;operator&gt;

&lt;text&gt;

&lt;concatenate&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;/concatenate&gt;

&lt;/text&gt;

&lt;/operator&gt;

&lt;operands&gt;

&lt;operand&gt;

&lt;value fieldRef="OWNER_1" dataProvider="custom"/&gt;

&lt;/operand&gt;

&lt;/operands&gt;

&lt;/expression&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="OWNER_1" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/PROFILE/@lastName" dataProvider="document"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;field id="USER_1" dataProvider="custom"&gt;

&lt;type&gt;

&lt;string align="none" length="10" case="none"&gt;

&lt;fromNumber decimalPlaces="1" groupSeparator="false" zeroPadding="false" approx="floor"/&gt;

&lt;/string&gt;

&lt;/type&gt;

&lt;assign&gt;

&lt;reference fieldRef="/FILE/DOCUMENT/TEMPLATE/ACCOUNT/@accountNumber" dataProvider="template"/&gt;

&lt;/assign&gt;

&lt;description/&gt;

&lt;/field&gt;

&lt;/printjobFields&gt;

&lt;documentFields/&gt;

&lt;envelopeFields/&gt;

&lt;lotFields/&gt;

&lt;spoolsetFields/&gt;

&lt;spoolfileFields/&gt;

&lt;templateFields/&gt;

&lt;pageFields/&gt;

&lt;/customFields&gt;

&lt;systemFields&gt;

&lt;printjobFields&gt;

&lt;systemField id="PJIndexRecsCountLOTXML_PRINT" defId="PJIndexRecsCount" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="PJIndexRecsCountTRACKING550P" defId="PJIndexRecsCount" instanceId="TRACKING550P"/&gt;

&lt;systemField id="PJIndexFileNameTRACKING550P" defId="PJIndexFileName" instanceId="TRACKING550P"/&gt;

&lt;systemField id="PJIndexFileNameTRACKING550E" defId="PJIndexFileName" instanceId="TRACKING550E"/&gt;

&lt;systemField id="PJIndexFileNameTRACKING550A" defId="PJIndexFileName" instanceId="TRACKING550A"/&gt;

&lt;systemField id="PJIndexFileNameTRACKING560A" defId="PJIndexFileName" instanceId="TRACKING560A"/&gt;

&lt;systemField id="PJIndexFullFileNameSME_FILE" defId="PJIndexFullFileName" instanceId="SME_FILE"/&gt;

&lt;systemField id="PJIndexFullFileNameSME_FILE_EMAIL" defId="PJIndexFullFileName" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="PJIndexRecsCountTRACKING550A" defId="PJIndexRecsCount" instanceId="TRACKING550A"/&gt;

&lt;systemField id="PJIndexFullFileNameLOTXML" defId="PJIndexFullFileName" instanceId="LOTXML"/&gt;

&lt;systemField id="PJIndexFullFileNameTRACKING560E" defId="PJIndexFullFileName" instanceId="TRACKING560E"/&gt;

&lt;systemField id="PJIndexFullFileNameTRACKING550P" defId="PJIndexFullFileName" instanceId="TRACKING550P"/&gt;

&lt;systemField id="PJIndexRecsCountTRACKING560A" defId="PJIndexRecsCount" instanceId="TRACKING560A"/&gt;

&lt;systemField id="PJIndexRecsCountDOCLIST" defId="PJIndexRecsCount" instanceId="DOCLIST"/&gt;

&lt;systemField id="PJIndexRecsCountLOTXML_ARCHIVE" defId="PJIndexRecsCount" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="PJIndexFullFileNameTRACKING550E" defId="PJIndexFullFileName" instanceId="TRACKING550E"/&gt;

&lt;systemField id="PJIndexRecsCountLOTXML" defId="PJIndexRecsCount" instanceId="LOTXML"/&gt;

&lt;systemField id="PJIndexFullFileNameLOTXML_ARCHIVE" defId="PJIndexFullFileName" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="PJIndexFullFileNameDOCLIST" defId="PJIndexFullFileName" instanceId="DOCLIST"/&gt;

&lt;systemField id="PJIndexFullFileNameTRACKING560A" defId="PJIndexFullFileName" instanceId="TRACKING560A"/&gt;

&lt;systemField id="PJIndexRecsCountTRACKING550E" defId="PJIndexRecsCount" instanceId="TRACKING550E"/&gt;

&lt;systemField id="PJIndexFileNameLOTXML_PRINT" defId="PJIndexFileName" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="PJIndexRecsCountTRACKING560P" defId="PJIndexRecsCount" instanceId="TRACKING560P"/&gt;

&lt;systemField id="PJIndexFileNameSME_FILE" defId="PJIndexFileName" instanceId="SME_FILE"/&gt;

&lt;systemField id="PJIndexRecsCountSME_FILE" defId="PJIndexRecsCount" instanceId="SME_FILE"/&gt;

&lt;systemField id="PJIndexFileNameSME_FILE_EMAIL" defId="PJIndexFileName" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="PJIndexFullFileNameEMAIL_BODY" defId="PJIndexFullFileName" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="PJIndexFullFileNameTRACKING550A" defId="PJIndexFullFileName" instanceId="TRACKING550A"/&gt;

&lt;systemField id="PJIndexFullFileNameLOTXML_PRINT" defId="PJIndexFullFileName" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="PJIndexFileNameDOCLIST" defId="PJIndexFileName" instanceId="DOCLIST"/&gt;

&lt;systemField id="PJIndexFullFileNameTRACKING560P" defId="PJIndexFullFileName" instanceId="TRACKING560P"/&gt;

&lt;systemField id="PJIndexRecsCountEMAIL_BODY" defId="PJIndexRecsCount" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="PJIndexFileNameEMAIL_BODY" defId="PJIndexFileName" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="PJIndexFileNameLOTXML" defId="PJIndexFileName" instanceId="LOTXML"/&gt;

&lt;systemField id="PJIndexRecsCountTRACKING560E" defId="PJIndexRecsCount" instanceId="TRACKING560E"/&gt;

&lt;systemField id="PJIndexFileNameTRACKING560P" defId="PJIndexFileName" instanceId="TRACKING560P"/&gt;

&lt;systemField id="PJIndexFileNameLOTXML_ARCHIVE" defId="PJIndexFileName" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="PJIndexFileNameTRACKING560E" defId="PJIndexFileName" instanceId="TRACKING560E"/&gt;

&lt;systemField id="PJIndexRecsCountSME_FILE_EMAIL" defId="PJIndexRecsCount" instanceId="SME_FILE_EMAIL"/&gt;

&lt;/printjobFields&gt;

&lt;documentFields/&gt;

&lt;envelopeFields/&gt;

&lt;lotFields&gt;

&lt;systemField id="LotNameDEFAULT" defId="LotName" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotEnveloper4BitsSeqNumberDEFAULT" defId="LotEnveloper4BitsSeqNumber" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotExtraPagesCounterDEFAULT" defId="LotExtraPagesCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPersCoverExtraSheetsCounterDEFAULT" defId="LotPersCoverExtraSheetsCounter" instanceId="

DEFAULT"/&gt;

&lt;systemField id="LotFillSheetsCounterDEFAULT" defId="LotFillSheetsCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotExtraSheetsCounterDEFAULT" defId="LotExtraSheetsCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotEnveloper4BitsGroupNumberDEFAULT" defId="LotEnveloper4BitsGroupNumber" instanceId="DEFAULT"

/&gt;

&lt;systemField id="LotSheetsCounter_PAGETAG2DEFAULT" defId="LotSheetsCounter_PAGETAG2" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPagesCounter_PAGETAG1DEFAULT" defId="LotPagesCounter_PAGETAG1" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotSheetsCounter_PAGETAG3DEFAULT" defId="LotSheetsCounter_PAGETAG3" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotSheetsCounter_PAGETAG1DEFAULT" defId="LotSheetsCounter_PAGETAG1" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPagesCounter_PAGETAG3DEFAULT" defId="LotPagesCounter_PAGETAG3" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotFillPagesCounterDEFAULT" defId="LotFillPagesCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotEnveloper3BitsGroupNumberDEFAULT" defId="LotEnveloper3BitsGroupNumber" instanceId="DEFAULT"

/&gt;

&lt;systemField id="LotCoverSheetsCounterDEFAULT" defId="LotCoverSheetsCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPagesCounter_PAGETAG4DEFAULT" defId="LotPagesCounter_PAGETAG4" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPersCoverExtraPagesCounterDEFAULT" defId="LotPersCoverExtraPagesCounter" instanceId="

DEFAULT"/&gt;

&lt;systemField id="LotCoverPagesCounterDEFAULT" defId="LotCoverPagesCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotSheetsCounter_PAGETAG4DEFAULT" defId="LotSheetsCounter_PAGETAG4" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPersCoverPagesCounterDEFAULT" defId="LotPersCoverPagesCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotIdDEFAULT" defId="LotId" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotEnvelopesCounterDEFAULT" defId="LotEnvelopesCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotEnveloper5BitsGroupNumberDEFAULT" defId="LotEnveloper5BitsGroupNumber" instanceId="DEFAULT"

/&gt;

&lt;systemField id="LotEnveloper5BitsSeqNumberDEFAULT" defId="LotEnveloper5BitsSeqNumber" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPagesCounter_PAGETAG2DEFAULT" defId="LotPagesCounter_PAGETAG2" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotEnveloper3BitsSeqNumberDEFAULT" defId="LotEnveloper3BitsSeqNumber" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPersonalizedSheetsCounterDEFAULT" defId="LotPersonalizedSheetsCounter" instanceId="DEFAULT"

/&gt;

&lt;systemField id="LotPersCoverSheetsCounterDEFAULT" defId="LotPersCoverSheetsCounter" instanceId="DEFAULT"/&gt;

&lt;systemField id="LotPersonalizedPagesCounterDEFAULT" defId="LotPersonalizedPagesCounter" instanceId="DEFAULT"/&gt;

&lt;/lotFields&gt;

&lt;spoolsetFields&gt;

&lt;systemField id="SSIndexFileNameTRACKING550P" defId="SSIndexFileName" instanceId="TRACKING550P"/&gt;

&lt;systemField id="SSIndexFileNameEMAIL_BODY" defId="SSIndexFileName" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="SSIndexFullFileNameSME_FILE_EMAIL" defId="SSIndexFullFileName" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="SSIndexRecsCountTRACKING560P" defId="SSIndexRecsCount" instanceId="TRACKING560P"/&gt;

&lt;systemField id="SSIndexFullFileNameLOTXML_PRINT" defId="SSIndexFullFileName" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="SSIndexRecsCountDOCLIST" defId="SSIndexRecsCount" instanceId="DOCLIST"/&gt;

&lt;systemField id="SSIndexFullFileNameTRACKING560P" defId="SSIndexFullFileName" instanceId="TRACKING560P"/&gt;

&lt;systemField id="SSIndexRecsCountEMAIL_BODY" defId="SSIndexRecsCount" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="SSIndexRecsCountSME_FILE" defId="SSIndexRecsCount" instanceId="SME_FILE"/&gt;

&lt;systemField id="SSIndexRecsCountTRACKING560A" defId="SSIndexRecsCount" instanceId="TRACKING560A"/&gt;

&lt;systemField id="SSIndexFileNameTRACKING550E" defId="SSIndexFileName" instanceId="TRACKING550E"/&gt;

&lt;systemField id="SSIndexFileNameTRACKING560E" defId="SSIndexFileName" instanceId="TRACKING560E"/&gt;

&lt;systemField id="SSIndexFileNameLOTXML" defId="SSIndexFileName" instanceId="LOTXML"/&gt;

&lt;systemField id="SSIndexFullFileNameLOTXML_ARCHIVE" defId="SSIndexFullFileName" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="SSIndexRecsCountTRACKING550A" defId="SSIndexRecsCount" instanceId="TRACKING550A"/&gt;

&lt;systemField id="SSIndexFileNameTRACKING560A" defId="SSIndexFileName" instanceId="TRACKING560A"/&gt;

&lt;systemField id="SSIndexFileNameLOTXML_PRINT" defId="SSIndexFileName" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="SSIndexFileNameSME_FILE" defId="SSIndexFileName" instanceId="SME_FILE"/&gt;

&lt;systemField id="SSIndexRecsCountTRACKING550P" defId="SSIndexRecsCount" instanceId="TRACKING550P"/&gt;

&lt;systemField id="SSIndexFileNameLOTXML_ARCHIVE" defId="SSIndexFileName" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="SSIndexFileNameTRACKING550A" defId="SSIndexFileName" instanceId="TRACKING550A"/&gt;

&lt;systemField id="SSIndexFileNameTRACKING560P" defId="SSIndexFileName" instanceId="TRACKING560P"/&gt;

&lt;systemField id="SSIndexFullFileNameEMAIL_BODY" defId="SSIndexFullFileName" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="SSIndexFullFileNameTRACKING550P" defId="SSIndexFullFileName" instanceId="TRACKING550P"/&gt;

&lt;systemField id="SSIndexFullFileNameTRACKING550E" defId="SSIndexFullFileName" instanceId="TRACKING550E"/&gt;

&lt;systemField id="SSIndexRecsCountLOTXML" defId="SSIndexRecsCount" instanceId="LOTXML"/&gt;

&lt;systemField id="SSIndexFileNameSME_FILE_EMAIL" defId="SSIndexFileName" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="SSIndexRecsCountLOTXML_ARCHIVE" defId="SSIndexRecsCount" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="SSIndexFullFileNameSME_FILE" defId="SSIndexFullFileName" instanceId="SME_FILE"/&gt;

&lt;systemField id="SSIndexRecsCountTRACKING550E" defId="SSIndexRecsCount" instanceId="TRACKING550E"/&gt;

&lt;systemField id="SSIndexFullFileNameLOTXML" defId="SSIndexFullFileName" instanceId="LOTXML"/&gt;

&lt;systemField id="SSIndexFullFileNameTRACKING560A" defId="SSIndexFullFileName" instanceId="TRACKING560A"/&gt;

&lt;systemField id="SSIndexRecsCountTRACKING560E" defId="SSIndexRecsCount" instanceId="TRACKING560E"/&gt;

&lt;systemField id="SSIndexRecsCountSME_FILE_EMAIL" defId="SSIndexRecsCount" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="SSIndexFullFileNameTRACKING550A" defId="SSIndexFullFileName" instanceId="TRACKING550A"/&gt;

&lt;systemField id="SSIndexFullFileNameTRACKING560E" defId="SSIndexFullFileName" instanceId="TRACKING560E"/&gt;

&lt;systemField id="SSIndexFileNameDOCLIST" defId="SSIndexFileName" instanceId="DOCLIST"/&gt;

&lt;systemField id="SSIndexRecsCountLOTXML_PRINT" defId="SSIndexRecsCount" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="SSIndexFullFileNameDOCLIST" defId="SSIndexFullFileName" instanceId="DOCLIST"/&gt;

&lt;/spoolsetFields&gt;

&lt;spoolfileFields&gt;

&lt;systemField id="SFIndexFileNameTRACKING550E" defId="SFIndexFileName" instanceId="TRACKING550E"/&gt;

&lt;systemField id="SFIndexFullFileNameTRACKING550E" defId="SFIndexFullFileName" instanceId="TRACKING550E"/&gt;

&lt;systemField id="SFIndexFullFileNameTRACKING550P" defId="SFIndexFullFileName" instanceId="TRACKING550P"/&gt;

&lt;systemField id="SFIndexFileNameLOTXML_PRINT" defId="SFIndexFileName" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="SFIndexFileNameSME_FILE_EMAIL" defId="SFIndexFileName" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="SFIndexFullFileNameLOTXML" defId="SFIndexFullFileName" instanceId="LOTXML"/&gt;

&lt;systemField id="SFIndexFileNameTRACKING560P" defId="SFIndexFileName" instanceId="TRACKING560P"/&gt;

&lt;systemField id="SFIndexRecsCountTRACKING550P" defId="SFIndexRecsCount" instanceId="TRACKING550P"/&gt;

&lt;systemField id="SFIndexRecsCountSME_FILE_EMAIL" defId="SFIndexRecsCount" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="SFIndexFullFileNameSME_FILE_EMAIL" defId="SFIndexFullFileName" instanceId="SME_FILE_EMAIL"/&gt;

&lt;systemField id="SFIndexFileNameTRACKING550A" defId="SFIndexFileName" instanceId="TRACKING550A"/&gt;

&lt;systemField id="SFIndexFileNameEMAIL_BODY" defId="SFIndexFileName" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="SFIndexFullFileNameSME_FILE" defId="SFIndexFullFileName" instanceId="SME_FILE"/&gt;

&lt;systemField id="SFIndexFullFileNameLOTXML_ARCHIVE" defId="SFIndexFullFileName" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="SFIndexFullFileNameTRACKING560A" defId="SFIndexFullFileName" instanceId="TRACKING560A"/&gt;

&lt;systemField id="SFIndexFileNameSME_FILE" defId="SFIndexFileName" instanceId="SME_FILE"/&gt;

&lt;systemField id="SFIndexFileNameDOCLIST" defId="SFIndexFileName" instanceId="DOCLIST"/&gt;

&lt;systemField id="SFIndexRecsCountLOTXML" defId="SFIndexRecsCount" instanceId="LOTXML"/&gt;

&lt;systemField id="SFIndexRecsCountSME_FILE" defId="SFIndexRecsCount" instanceId="SME_FILE"/&gt;

&lt;systemField id="SFIndexRecsCountEMAIL_BODY" defId="SFIndexRecsCount" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="SFIndexRecsCountTRACKING560E" defId="SFIndexRecsCount" instanceId="TRACKING560E"/&gt;

&lt;systemField id="SFIndexRecsCountTRACKING560P" defId="SFIndexRecsCount" instanceId="TRACKING560P"/&gt;

&lt;systemField id="SFIndexFullFileNameDOCLIST" defId="SFIndexFullFileName" instanceId="DOCLIST"/&gt;

&lt;systemField id="SFIndexFullFileNameTRACKING560P" defId="SFIndexFullFileName" instanceId="TRACKING560P"/&gt;

&lt;systemField id="SFIndexFullFileNameTRACKING560E" defId="SFIndexFullFileName" instanceId="TRACKING560E"/&gt;

&lt;systemField id="SFIndexRecsCountTRACKING550E" defId="SFIndexRecsCount" instanceId="TRACKING550E"/&gt;

&lt;systemField id="SFIndexFileNameTRACKING550P" defId="SFIndexFileName" instanceId="TRACKING550P"/&gt;

&lt;systemField id="SFIndexRecsCountLOTXML_ARCHIVE" defId="SFIndexRecsCount" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="SFIndexFullFileNameLOTXML_PRINT" defId="SFIndexFullFileName" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="SFIndexRecsCountLOTXML_PRINT" defId="SFIndexRecsCount" instanceId="LOTXML_PRINT"/&gt;

&lt;systemField id="SFIndexFileNameTRACKING560A" defId="SFIndexFileName" instanceId="TRACKING560A"/&gt;

&lt;systemField id="SFIndexFullFileNameTRACKING550A" defId="SFIndexFullFileName" instanceId="TRACKING550A"/&gt;

&lt;systemField id="SFIndexRecsCountDOCLIST" defId="SFIndexRecsCount" instanceId="DOCLIST"/&gt;

&lt;systemField id="SFIndexRecsCountTRACKING560A" defId="SFIndexRecsCount" instanceId="TRACKING560A"/&gt;

&lt;systemField id="SFIndexFileNameTRACKING560E" defId="SFIndexFileName" instanceId="TRACKING560E"/&gt;

&lt;systemField id="SFIndexFullFileNameEMAIL_BODY" defId="SFIndexFullFileName" instanceId="EMAIL_BODY"/&gt;

&lt;systemField id="SFIndexRecsCountTRACKING550A" defId="SFIndexRecsCount" instanceId="TRACKING550A"/&gt;

&lt;systemField id="SFIndexFileNameLOTXML_ARCHIVE" defId="SFIndexFileName" instanceId="LOTXML_ARCHIVE"/&gt;

&lt;systemField id="SFIndexFileNameLOTXML" defId="SFIndexFileName" instanceId="LOTXML"/&gt;

&lt;/spoolfileFields&gt;

&lt;templateFields/&gt;

&lt;pageFields/&gt;

&lt;/systemFields&gt;

&lt;lots&gt;

&lt;lot id="DEFAULT" name="DEFAULT"/&gt;

&lt;/lots&gt;

&lt;envelopeManagement&gt;

&lt;envelopeCreation&gt;

&lt;envelopeCapacity fieldRef="PJConstantZero" dataProvider="system"/&gt;

&lt;multienvelope fieldRef="PJConstantFalse" dataProvider="system"/&gt;

&lt;useCover fieldRef="PJConstantFalse" dataProvider="system"/&gt;

&lt;coverOnFirstEnvelope fieldRef="PJConstantFalse" dataProvider="system"/&gt;

&lt;envelopeExtraSheets&gt;

&lt;firstEnvelope fieldRef="PJConstantZero" dataProvider="system"/&gt;

&lt;allEnvelopes fieldRef="PJConstantZero" dataProvider="system"/&gt;

&lt;/envelopeExtraSheets&gt;

&lt;/envelopeCreation&gt;

&lt;envelopeDispatching&gt;

&lt;destinationLot fieldRef="LOT_NAME" dataProvider="custom"/&gt;

&lt;/envelopeDispatching&gt;

&lt;envelopeInserts enabled="false"&gt;

&lt;Insert1&gt;

&lt;label/&gt;

&lt;enableOnFirstEnvelope/&gt;

&lt;enableOnAllEnvelopes/&gt;

&lt;sheetsCount/&gt;

&lt;/Insert1&gt;

&lt;Insert2&gt;

&lt;label/&gt;

&lt;enableOnFirstEnvelope/&gt;

&lt;enableOnAllEnvelopes/&gt;

&lt;sheetsCount/&gt;

&lt;/Insert2&gt;

&lt;Insert3&gt;

&lt;label/&gt;

&lt;enableOnFirstEnvelope/&gt;

&lt;enableOnAllEnvelopes/&gt;

&lt;sheetsCount/&gt;

&lt;/Insert3&gt;

&lt;Insert4&gt;

&lt;label/&gt;

&lt;enableOnFirstEnvelope/&gt;

&lt;enableOnAllEnvelopes/&gt;

&lt;sheetsCount/&gt;

&lt;/Insert4&gt;

&lt;/envelopeInserts&gt;

&lt;/envelopeManagement&gt;

&lt;trayManagement enabled="false" defaultTray="1" modality="static"/&gt;

&lt;fileManagement&gt;

&lt;fileManagementConfiguration id="PRINT" name="PRINT" errorManagement="stop" spoolingOnError="true"

reduceWorkingSpace="true"&gt;

&lt;printjob&gt;

&lt;index name="TRACKING550" id="TRACKING550P" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="TR550_FILENAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_02_LOTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_03_CLIENTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_04_ACCOUNTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_05_JOBID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_06_WORKTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_07_WORKSTAGE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_08_OWNER" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_09_HOSTNAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_10_APPTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_11_PROCEDURE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_12_PROCVERS" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_13_JOBRESULT" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_14_AUTOCLOSE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_15_CUSTOM01" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_16_CUSTOM02" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_17_CUSTOM03" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_18_CUSTOM04" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_19_CUSTOM05" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_02_ID_ISTANZA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_04_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_05_NOME_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_06_SIZE_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_07_CODICE_P_P" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_08_ID_CONTAIN" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_09_NOME_CONTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_10_TS_CREAZIO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_12_FILENAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_13_FILEPATH" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_14_FILE_SIZE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_15_FILE_TYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_16_ID_PROD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_17_TS_INIZIO_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_18_TS_FINE_JO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_19_RECORD_STA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_20_RECORD_END" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_21_PROGRESSIV" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_22_PROGRESSIV" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_23_DOCUMENTI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_24_PAGINE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_25_PAGINE_BIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_26_FOGLI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_27_BOLLETTINI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_28_VIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_29_CAP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_30_LOCALITA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_31_PROVINCIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_32_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_33_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_34_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_35_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_36_TIPO_DOCUM" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_37_CANALE_P" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_38_FORMATO_P" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_39_EMISSIONE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_40_SOCIETA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_41_DIVISIONE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_42_MERCATO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_43_IMPORTO_TO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_44_CODICE_MOD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_45_CODICE_COL" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_46_CODICE_DUP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_47_NUMRACCAND" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_48_NUMRACCRIT" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_49_BARCODE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_50_AREA_POSTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_51_PESO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_52_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_53_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_54_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_55_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_56_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_57_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_58_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_59_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_60_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_61_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_62_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_63_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_64_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_65_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_66_ID_SUB_PRO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_67_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;index name="TRACKING560" id="TRACKING560P" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="TR560_FILENAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_01_ID_BUSTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_02_ID_DOCUMEN" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_03_CODICE_MOD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_04_TIPOLOGIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_05_ID_ACQUISI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_06_DATA_SCADE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_07_DATA_EMISS" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_08_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_09_CODICE_DES" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_10_NOME_DESTI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_11_PIVACF_DES" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_12_IMPORTO_PA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_13_PESO_DOCUM" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_14_PRESENZA_B" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_15_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;dataTracing enabled="false" respectBreakRules="false"&gt;

&lt;dataTraceFile/&gt;

&lt;/dataTracing&gt;

&lt;/printjob&gt;

&lt;spoolsets multiple="false"&gt;

&lt;spoolset splitResolution="template" id="DEFAULT" suppressBackPages="false" trailingSheet="false" leadingSheet="false"&gt;

&lt;index name="SME_FILE" id="SME_FILE" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType=" tle" hierarchical="false"&gt;

&lt;fileName fieldRef="PRINT_SME_NAME" dataProvider="custom"/&gt;

&lt;spoolsetEnd&gt;

&lt;record terminator="crlf" name="SME Content" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="PRINT_SME_NAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolsetEnd&gt;

&lt;/index&gt;

&lt;index name="LOTXML_PRINT" id="LOTXML_PRINT" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="PRINT_LOTXML_NAME" dataProvider="custom"/&gt;

&lt;spoolsetEnd&gt;

&lt;record terminator="crlf" name="LOTXML Content" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="PRINT_LOTXML_BODY_RE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolsetEnd&gt;

&lt;/index&gt;

&lt;spoolfiles&gt;

&lt;fileName fieldRef="PRINT_FILE_NAME" dataProvider="custom"/&gt;

&lt;/spoolfiles&gt;

&lt;security&gt;

&lt;zipPasswordField fieldRef="PJAbsOutputPath" dataProvider="system"/&gt;

&lt;enableZipPassword&gt;false&lt;/enableZipPassword&gt;

&lt;requirePasswordToOpen&gt;true&lt;/requirePasswordToOpen&gt;

&lt;passwordToOpen fieldRef="PWD_USER_DATAFILE" dataProvider="custom"/&gt;

&lt;requirePasswordToOp&gt;true&lt;/requirePasswordToOp&gt;

&lt;passwordToOp fieldRef="PWD_OWNER_DATAFILE" dataProvider="custom"/&gt;

&lt;allowPrinting&gt;false&lt;/allowPrinting&gt;

&lt;allowEditing&gt;true&lt;/allowEditing&gt;

&lt;allowCopying&gt;false&lt;/allowCopying&gt;

&lt;allowAnnotationEditing&gt;false&lt;/allowAnnotationEditing&gt;

&lt;/security&gt;

&lt;spoolfilesettings enableFillerPages="false" fillerPagesPerPrint="2" startShipmentOnPage="2"&gt;

&lt;fillerPagesActivationAttribute/&gt;

&lt;/spoolfilesettings&gt;

&lt;outputPackaging enabled="false" afterEntity="shipment" enableCrypt="false" compressionMethod="zip"&gt;

&lt;outputFileName/&gt;

&lt;outputPassword/&gt;

&lt;sourceFolder/&gt;

&lt;/outputPackaging&gt;

&lt;/spoolset&gt;

&lt;/spoolsets&gt;

&lt;lotMD enabled="true"&gt;

&lt;path/&gt;

&lt;filename/&gt;

&lt;producer&gt;

&lt;bomId/&gt;

&lt;environmentDn/&gt;

&lt;useCase&gt;ONDEMAND&lt;/useCase&gt;

&lt;/producer&gt;

&lt;externalId/&gt;

&lt;priority&gt;LOWEST&lt;/priority&gt;

&lt;messages&gt;

&lt;message&gt;

&lt;gateways&gt;

&lt;email enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/email&gt;

&lt;pec enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/pec&gt;

&lt;sms enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients&gt;

&lt;recipient&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;type&gt;TO&lt;/type&gt;

&lt;/recipient&gt;

&lt;/recipients&gt;

&lt;body&gt;

&lt;text&gt;

&lt;path/&gt;

&lt;/text&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/sms&gt;

&lt;purl enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/purl&gt;

&lt;fax enabled="false"&gt;

&lt;destination/&gt;

&lt;files&gt;

&lt;file&gt;

&lt;remoteSubpath/&gt;

&lt;path/&gt;

&lt;/file&gt;

&lt;/files&gt;

&lt;sender/&gt;

&lt;quality&gt;medium&lt;/quality&gt;

&lt;/fax&gt;

&lt;fileshare enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;

&lt;remoteSubpath/&gt;

&lt;files/&gt;

&lt;/fileshare&gt;

&lt;ftp enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;

&lt;remoteSubpath/&gt;

&lt;files/&gt;

&lt;/ftp&gt;

&lt;/gateways&gt;

&lt;properties&gt;

&lt;property name="ID_OBJECT"&gt;

&lt;value/&gt;

&lt;/property&gt;

&lt;/properties&gt;

&lt;/message&gt;

&lt;/messages&gt;

&lt;/lotMD&gt;

&lt;DAConfiguration enabled="false"/&gt;

&lt;/fileManagementConfiguration&gt;

&lt;fileManagementConfiguration id="EMAIL" name="EMAIL" errorManagement="stop" spoolingOnError="true" reduceWorkingSpace="true"&gt;

&lt;printjob&gt;

&lt;index name="TRACKING550" id="TRACKING550E" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="TR550_FILENAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_02_LOTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_03_CLIENTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_04_ACCOUNTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_05_JOBID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_06_WORKTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_07_WORKSTAGE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_08_OWNER" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_09_HOSTNAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_10_APPTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_11_PROCEDURE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_12_PROCVERS" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_13_JOBRESULT" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_14_AUTOCLOSE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_15_CUSTOM01" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_16_CUSTOM02" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_17_CUSTOM03" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_18_CUSTOM04" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_19_CUSTOM05" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_02_ID_ISTANZA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_04_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_05_NOME_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_06_SIZE_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_07_CODICE_P_E" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_08_ID_CONTAIN" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_09_NOME_CONTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_10_TS_CREAZIO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_12_FILENAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_13_FILEPATH" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_14_FILE_SIZE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_15_FILE_TYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_16_ID_PROD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_17_TS_INIZIO_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_18_TS_FINE_JO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_19_RECORD_STA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_20_RECORD_END" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_21_PROGRESSIV" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_22_PROGRESSIV" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_23_DOCUMENTI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_24_PAGINE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_25_PAGINE_BIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_26_FOGLI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_27_BOLLETTINI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_28_VIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_29_CAP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_30_LOCALITA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_31_PROVINCIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_32_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_33_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_34_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_35_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_36_TIPO_DOCUM" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_37_CANALE_E" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_38_FORMATO_E" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_39_EMISSIONE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_40_SOCIETA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_41_DIVISIONE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_42_MERCATO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_43_IMPORTO_TO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_44_CODICE_MOD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_45_CODICE_COL" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_46_CODICE_DUP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_47_NUMRACCAND" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_48_NUMRACCRIT" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_49_BARCODE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_50_AREA_POSTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_51_PESO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_52_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_53_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_54_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_55_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_56_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_57_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_58_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_59_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_60_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_61_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_62_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_63_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_64_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_65_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_66_ID_SUB_PRO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_67_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;index name="TRACKING560" id="TRACKING560E" enabled="true" insideSpool="false" encoding="ansi"

indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="TR560_FILENAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_01_ID_BUSTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_02_ID_DOCUMEN" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_03_CODICE_MOD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_04_TIPOLOGIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_05_ID_ACQUISI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_06_DATA_SCADE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_07_DATA_EMISS" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_08_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_09_CODICE_DES" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_10_NOME_DESTI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_11_PIVACF_DES" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_12_IMPORTO_PA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_13_PESO_DOCUM" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_14_PRESENZA_B" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_15_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;dataTracing enabled="false" respectBreakRules="false"&gt;

&lt;dataTraceFile/&gt;

&lt;/dataTracing&gt;

&lt;/printjob&gt;

&lt;spoolsets multiple="false"&gt;

&lt;spoolset splitResolution="envelope" id="DEFAULT" suppressBackPages="false" trailingSheet="false" leadingSheet="false"&gt;

&lt;index name="LOTXML" id="LOTXML" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="EMAIL_LOTXML_NAME" dataProvider="custom"/&gt;

&lt;envelopeEnd&gt;

&lt;record terminator="crlf" name="Lotxml message" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="EMAIL_LOTXML_BODY_RE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/envelopeEnd&gt;

&lt;spoolsetStart&gt;

&lt;record terminator="crlf" name="Lotxml header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="EMAIL_LOTXML_HEADER" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolsetStart&gt;

&lt;spoolsetEnd&gt;

&lt;record terminator="crlf" name="Lotxml footer" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="EMAIL_LOTXML_FOOT_RE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolsetEnd&gt;

&lt;/index&gt;

&lt;index name="SME_FILE_EMAIL" id="SME_FILE_EMAIL" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="EMAIL_SEMAPHORE_NAME" dataProvider="custom"/&gt;

&lt;spoolsetEnd&gt;

&lt;record terminator="crlf" name="new record" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;const&gt;c21l&lt;/const&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolsetEnd&gt;

&lt;/index&gt;

&lt;spoolfiles&gt;

&lt;fileName fieldRef="EMAIL_SPOOL_NAME" dataProvider="custom"/&gt;

&lt;index name="EMAIL_BODY" id="EMAIL_BODY" enabled="true" insideSpool="false" encoding="ansi"

indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="EMAIL_BODY_NAME" dataProvider="custom"/&gt;

&lt;spoolfileEnd&gt;

&lt;record terminator="crlf" name="new record" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="EMAIL_BODY_CONT_RE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolfileEnd&gt;

&lt;/index&gt;

&lt;/spoolfiles&gt;

&lt;security&gt;

&lt;zipPasswordField/&gt;

&lt;enableZipPassword&gt;false&lt;/enableZipPassword&gt;

&lt;requirePasswordToOpen&gt;false&lt;/requirePasswordToOpen&gt;

&lt;passwordToOpen/&gt;

&lt;requirePasswordToOp&gt;false&lt;/requirePasswordToOp&gt;

&lt;passwordToOp/&gt;

&lt;allowPrinting&gt;true&lt;/allowPrinting&gt;

&lt;allowEditing&gt;true&lt;/allowEditing&gt;

&lt;allowCopying&gt;true&lt;/allowCopying&gt;

&lt;allowAnnotationEditing&gt;true&lt;/allowAnnotationEditing&gt;

&lt;/security&gt;

&lt;spoolfilesettings enableFillerPages="false" fillerPagesPerPrint="2" startShipmentOnPage="2"&gt;

&lt;fillerPagesActivationAttribute/&gt;

&lt;/spoolfilesettings&gt;

&lt;outputPackaging enabled="false" afterEntity="shipment" enableCrypt="false" compressionMethod="zip"&gt;

&lt;outputFileName/&gt;

&lt;outputPassword/&gt;

&lt;sourceFolder/&gt;

&lt;/outputPackaging&gt;

&lt;/spoolset&gt;

&lt;/spoolsets&gt;

&lt;lotMD enabled="false"&gt;

&lt;path/&gt;

&lt;filename/&gt;

&lt;producer&gt;

&lt;bomId/&gt;

&lt;environmentDn/&gt;

&lt;useCase&gt;ONDEMAND&lt;/useCase&gt;

&lt;/producer&gt;

&lt;externalId/&gt;

&lt;priority&gt;LOWEST&lt;/priority&gt;

&lt;messages&gt;

&lt;message&gt;

&lt;gateways&gt;

&lt;email enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/email&gt;

&lt;pec enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/pec&gt;

&lt;sms enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;text&gt;

&lt;path/&gt;

&lt;/text&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/sms&gt;

&lt;purl enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/purl&gt;

&lt;fax enabled="false"&gt;

&lt;destination/&gt;

&lt;files&gt;

&lt;file&gt;

&lt;remoteSubpath/&gt;

&lt;path/&gt;

&lt;/file&gt;

&lt;/files&gt;

&lt;sender/&gt;

&lt;quality&gt;medium&lt;/quality&gt;

&lt;/fax&gt;

&lt;fileshare enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;

&lt;remoteSubpath/&gt;

&lt;files/&gt;

&lt;/fileshare&gt;

&lt;ftp enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;

&lt;remoteSubpath/&gt;

&lt;files/&gt;

&lt;/ftp&gt;

&lt;/gateways&gt;

&lt;properties&gt;

&lt;property name="ID_OBJECT"&gt;

&lt;value/&gt;

&lt;/property&gt;

&lt;/properties&gt;

&lt;/message&gt;

&lt;/messages&gt;

&lt;/lotMD&gt;

&lt;DAConfiguration enabled="false"/&gt;

&lt;/fileManagementConfiguration&gt;

&lt;fileManagementConfiguration id="ARCHIVE" name="ARCHIVE" errorManagement="stop" spoolingOnError="true" reduceWorkingSpace="true"&gt;

&lt;printjob&gt;

&lt;index name="TRACKING550" id="TRACKING550A" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="TR550_FILENAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_02_LOTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_03_CLIENTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_04_ACCOUNTID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_05_JOBID" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_06_WORKTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_07_WORKSTAGE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_08_OWNER" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_09_HOSTNAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_10_APPTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_11_PROCEDURE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_12_PROCVERS" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_13_JOBRESULT" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_14_AUTOCLOSE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_15_CUSTOM01" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_16_CUSTOM02" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_17_CUSTOM03" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_18_CUSTOM04" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550H_19_CUSTOM05" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_02_ID_ISTANZA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_03_ID_MISSIVA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_04_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_05_NOME_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_06_SIZE_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_07_CODICE_P_A" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_08_ID_CONTAIN" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_09_NOME_CONTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_10_TS_CREAZIO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_11_ID_SOURCE_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_12_FILENAME" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_13_FILEPATH" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_14_FILE_SIZE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_15_FILE_TYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_16_ID_PROD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_17_TS_INIZIO_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_18_TS_FINE_JO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_19_RECORD_STA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_20_RECORD_END" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_21_PROGRESSIV" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_22_PROGRESSIV" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_23_DOCUMENTI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_24_PAGINE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_25_PAGINE_BIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_26_FOGLI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_27_BOLLETTINI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_28_VIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_29_CAP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_30_LOCALITA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_31_PROVINCIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_32_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_33_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_34_ANAGRAFICA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_35_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_36_TIPO_DOCUM" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_37_CANALE_A" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_38_FORMATO_A" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_39_EMISSIONE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_40_SOCIETA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_41_DIVISIONE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_42_MERCATO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_43_IMPORTO_TO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_44_CODICE_MOD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_45_CODICE_COL" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_46_CODICE_DUP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_47_NUMRACCAND" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_48_NUMRACCRIT" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_49_BARCODE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_50_AREA_POSTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_51_PESO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_52_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_53_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_54_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_55_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_56_ALLEGATI_T" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_57_NUM_ALLEGA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_58_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_59_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_60_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_61_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_62_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_63_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_64_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_65_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_66_ID_SUB_PRO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR550D_67_CUSTOM_VC_" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;index name="TRACKING560" id="TRACKING560A" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="TR560_FILENAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="Header" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="Detail" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength&gt;

&lt;separator&gt;fA==&lt;/separator&gt;

&lt;/variableLength&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_00_RECORDTYPE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_01_ID_BUSTA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_02_ID_DOCUMEN" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_03_CODICE_MOD" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_04_TIPOLOGIA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_05_ID_ACQUISI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_06_DATA_SCADE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_07_DATA_EMISS" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_08_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_09_CODICE_DES" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_10_NOME_DESTI" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_11_PIVACF_DES" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_12_IMPORTO_PA" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_13_PESO_DOCUM" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_14_PRESENZA_B" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560D_15_CODICE_DOC" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_01_ID_JOB" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="TR560H_02_ID_LOTTO" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;index name="DOCLIST" id="DOCLIST" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

Pg==&lt;/const&gt;

&lt;fileName fieldRef="DOCLIST_FILE_NAME" dataProvider="custom"/&gt;

&lt;printjobStart&gt;

&lt;record terminator="crlf" name="&amp;lt;?xml" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;const&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iSVNPODg1OS0xIiBzdGFuZGFsb25lPSJubyI/

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;record terminator="crlf" name="&amp;lt;doclist&gt;" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;const&gt;PGRvY2xpc3QgdGltZXN0YW1wPSI=&lt;/const&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;value fieldRef="PJStartTimestamp" dataProvider="system"/&gt;

&lt;/item&gt;

&lt;item&gt;

&lt;const&gt;Ij4=&lt;/const&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobStart&gt;

&lt;printjobEnd&gt;

&lt;record terminator="crlf" name="&amp;lt;/doclist&gt;" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;const&gt;PC9kb2NsaXN0Pg==&lt;/const&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/printjobEnd&gt;

&lt;documentEnd&gt;

&lt;record terminator="crlf" name="&amp;lt;document/&gt;" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="DOCLIST_DOCUMENT_REP" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/documentEnd&gt;

&lt;/index&gt;

&lt;dataTracing enabled="false" respectBreakRules="false"&gt;

&lt;dataTraceFile/&gt;

&lt;/dataTracing&gt;

&lt;/printjob&gt;

&lt;spoolsets multiple="false"&gt;

&lt;spoolset splitResolution="document" id="DEFAULT" suppressBackPages="false" trailingSheet="false" leadingSheet="false"&gt;

&lt;index name="LOTXML_ARCHIVE" id="LOTXML_ARCHIVE" enabled="true" insideSpool="false" encoding="ansi" indexSpoolType="tle" hierarchical="false"&gt;

&lt;fileName fieldRef="ARCH_LOTXML_NAME" dataProvider="custom"/&gt;

&lt;spoolsetEnd&gt;

&lt;record terminator="crlf" name="LOTXML Content" groupable="0" useEnabling="false"&gt;

&lt;appendMode&gt;

&lt;variableLength/&gt;

&lt;/appendMode&gt;

&lt;enablingAttribute/&gt;

&lt;items&gt;

&lt;item&gt;

&lt;value fieldRef="ARCH_LOTXML_BODY_RE" dataProvider="custom"/&gt;

&lt;/item&gt;

&lt;/items&gt;

&lt;/record&gt;

&lt;/spoolsetEnd&gt;

&lt;/index&gt;

&lt;spoolfiles&gt;

&lt;fileName fieldRef="ARCH_SPOOL_NAME" dataProvider="custom"/&gt;

&lt;/spoolfiles&gt;

&lt;security&gt;

&lt;zipPasswordField/&gt;

&lt;enableZipPassword&gt;false&lt;/enableZipPassword&gt;

&lt;requirePasswordToOpen&gt;false&lt;/requirePasswordToOpen&gt;

&lt;passwordToOpen fieldRef="OWNER_PW" dataProvider="custom"/&gt;

&lt;requirePasswordToOp&gt;false&lt;/requirePasswordToOp&gt;

&lt;passwordToOp fieldRef="USER_PW" dataProvider="custom"/&gt;

&lt;allowPrinting&gt;true&lt;/allowPrinting&gt;

&lt;allowEditing&gt;true&lt;/allowEditing&gt;

&lt;allowCopying&gt;true&lt;/allowCopying&gt;

&lt;allowAnnotationEditing&gt;true&lt;/allowAnnotationEditing&gt;

&lt;/security&gt;

&lt;spoolfilesettings enableFillerPages="false" fillerPagesPerPrint="2" startShipmentOnPage="2"&gt;

&lt;fillerPagesActivationAttribute/&gt;

&lt;/spoolfilesettings&gt;

&lt;outputPackaging enabled="false" afterEntity="shipment" enableCrypt="false" compressionMethod="zip"&gt;

&lt;outputFileName/&gt;

&lt;outputPassword/&gt;

&lt;sourceFolder/&gt;

&lt;/outputPackaging&gt;

&lt;/spoolset&gt;

&lt;/spoolsets&gt;

&lt;lotMD enabled="false"&gt;

&lt;path/&gt;

&lt;filename/&gt;

&lt;producer&gt;

&lt;bomId/&gt;

&lt;environmentDn/&gt;

&lt;useCase&gt;ONDEMAND&lt;/useCase&gt;

&lt;/producer&gt;

&lt;externalId/&gt;

&lt;priority&gt;LOWEST&lt;/priority&gt;

&lt;messages&gt;

&lt;message&gt;

&lt;gateways&gt;

&lt;email enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/email&gt;

&lt;pec enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/pec&gt;

&lt;sms enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;text&gt;

&lt;path/&gt;

&lt;/text&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/sms&gt;

&lt;purl enabled="false"&gt;

&lt;codepage&gt;UTF-8&lt;/codepage&gt;

&lt;subject/&gt;

&lt;recipients/&gt;

&lt;body&gt;

&lt;html&gt;

&lt;path/&gt;

&lt;/html&gt;

&lt;/body&gt;

&lt;attachments/&gt;

&lt;from&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/from&gt;

&lt;replyTo&gt;

&lt;address/&gt;

&lt;name/&gt;

&lt;/replyTo&gt;

&lt;priority&gt;NORMAL&lt;/priority&gt;

&lt;x-headers/&gt;

&lt;emailUsername/&gt;

&lt;emailPassword/&gt;

&lt;emailMessageId/&gt;

&lt;/purl&gt;

&lt;fax enabled="false"&gt;

&lt;destination/&gt;

&lt;files&gt;

&lt;file&gt;

&lt;remoteSubpath/&gt;

&lt;path/&gt;

&lt;/file&gt;

&lt;/files&gt;

&lt;sender/&gt;

&lt;quality&gt;medium&lt;/quality&gt;

&lt;/fax&gt;

&lt;fileshare enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;

&lt;remoteSubpath/&gt;

&lt;files/&gt;

&lt;/fileshare&gt;

&lt;ftp enabled="false" onlyOne="true" oneForSpoolFile="false"&gt;

&lt;remoteSubpath/&gt;

&lt;files/&gt;

&lt;/ftp&gt;

&lt;/gateways&gt;

&lt;properties&gt;

&lt;property name="ID_OBJECT"&gt;

&lt;value/&gt;

&lt;/property&gt;

&lt;/properties&gt;

&lt;/message&gt;

&lt;/messages&gt;

&lt;/lotMD&gt;

&lt;DAConfiguration enabled="false"/&gt;

&lt;/fileManagementConfiguration&gt;

&lt;/fileManagement&gt;

&lt;overprintManagement&gt;

&lt;overprintManagementConfiguration id="PRINT" name="PRINT"&gt;

&lt;printjob&gt;

&lt;document&gt;

&lt;allSheets/&gt;

&lt;firstSheet&gt;

&lt;front&gt;PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiID8+CjxyZXNvdXJjZSBsaWJyYXJ5 X2lkPSIwIiBleGFjdEhlaWdodD0iMTY5NTQ5IiBleGFjdFdpZHRoPSI5Mzk1MCIgd2lyZWZyYW1l SGVpZ2h0PSIxNjk1NDkiIHdpcmVmcmFtZVdpZHRoPSI5Mzk1MCI+CiAgPHN3aW1sYW5lIGhlaWdo dD0iMTY5NTQ5IiB5PSIwIj4KICAgIDxlbGVtZW50IHg9IjIzMDAwIiB5PSIyNjgyOCIgd2lkdGg9 IjcwOTUwIiBoZWlnaHQ9IjE0NzMyIiBvcmRlcj0iMSIgaWQ9IjAuMjM2NzM0Njc2NjQwNDgwNzYi IGRlYnVnPSJmYWxzZSIgcm90YXRpb249IjAiPgogICAgICA8ZHJhdz4KICAgICAgICA8YmFyY29k ZSB2YXJkYXRhSWQ9IjU5NCIgdmFyZGF0YVBsYWNlaG9sZGVyPSJJTUJfVkFMVUUiIHR5cGVJZD0i

MyIgZmFtaWx5PSIxZCIgdHlwZT0iaW1iIiByZW5kZXJzdHJpbmc9IlxcQmVnaW57NFNUQVRFfVxc bV9uQmFyQ29kZUlEezcwNX1cXG1fbkJhckNvZGVUeXBlezN9XFxtX3N6VGV4dHswMTIzNDU2NzA5 NDk4NzY1NDMyMTAxMjM0NTY3ODkxfVxcbV9uVGV4dExlbmd0aHszMX1cXG1fY1Byb21wdENoYXJ7 MTIwfVxcbV9uTWVhc3VyZVR5cGV7Mn1cXG1fblByaW50ZXJSZXNvbHV0aW9uezMwMH1cXG1fbkhl aWdodEluRG90c3s0NH1cXG1fbldpZHRoSW5Eb3RzezgzOH1cXG1fbkJhcldpZHRoezUwfVxcbV9u QXNjZW5kZXJIZWlnaHR7MTIzfVxcbV9uVHJhY2tIZWlnaHR7MTIxfVxcbV9uRGVzY2VuZGVySGVp Z2h0ezEyM31cXG1fbkJhclBpdGNoezIyfVxcbV9uRW5jb2RpbmdUYWJsZXstMX1cXG1fbkZDQ3st MX1cXEVuZHs0U1RBVEV9IiBhbGxvd0hlaWdodENoYW5nZT0idHJ1ZSIgYWxsb3dlZERhdGFUeXBl PSJudW1lcmljb25seSIgYWxsb3dPZGRDaGFycz0iZmFsc2UiIG1pbkxlbmd0aD0iMzIiIG1heExl bmd0aD0iMzIiLz4KICAgICAgPC9kcmF3PgogICAgPC9lbGVtZW50PgogICAgPGVsZW1lbnQgeD0i MCIgeT0iNzk1NDkiIHdpZHRoPSIxMDAwMCIgaGVpZ2h0PSIxMDAwMCIgb3JkZXI9IjIiIGlkPSIw LjYwOTQyMDQ3NzQxMjY0MSIgZGVidWc9InRydWUiIHJvdGF0aW9uPSIwIj4KICAgICAgPGRyYXcg c3Ryb2tlPSJmYWxzZSIgc3Ryb2tlQ29sb3I9IjB4MCIgc3Ryb2tlV2VpZ2h0PSIzMDAiPgogICAg ICAgIDxiYXJzZXQgZ2FwPSIxMDAwMCIgd2VpZ2h0PSI2MDAiLz4KICAgICAgPC9kcmF3PgogICAg PC9lbGVtZW50PgogIDwvc3dpbWxhbmU+CjwvcmVzb3VyY2U+&lt;/front&gt;

&lt;/firstSheet&gt;

&lt;lastSheet/&gt;

&lt;/document&gt;

&lt;envelope&gt;

&lt;allSheets/&gt;

&lt;firstSheet/&gt;

&lt;lastSheet/&gt;

&lt;/envelope&gt;

&lt;header&gt;

&lt;allSheets/&gt;

&lt;firstSheet/&gt;

&lt;lastSheet/&gt;

&lt;/header&gt;

&lt;trailer&gt;

&lt;allSheets/&gt;

&lt;firstSheet/&gt;

&lt;lastSheet/&gt;

&lt;/trailer&gt;

&lt;fillerPage&gt;

&lt;allSheets/&gt;

&lt;firstSheet/&gt;

&lt;lastSheet/&gt;

&lt;/fillerPage&gt;

&lt;/printjob&gt;

&lt;lots&gt;

&lt;lot lotId="DEFAULT"&gt;

&lt;envelope&gt;

&lt;allSheets/&gt;

&lt;firstSheet/&gt;

&lt;lastSheet/&gt;

&lt;/envelope&gt;

&lt;/lot&gt;

&lt;/lots&gt;

&lt;/overprintManagementConfiguration&gt;

&lt;/overprintManagement&gt;

&lt;/serializer&gt;

&lt;/serializers&gt;

&lt;omsf:fieldsConfig [xmlns:omsf="http://www.ebilling.it/eDoc2/OutputManagementSystemFields"](http://www.ebilling.it/eDoc2/OutputManagementSystemFields) [xmlns:xsi="http://www.w3.org](http://www.w3.org/)

/2001/XMLSchema-instance"&gt;

&lt;omsf:field varName="TargetCountry" varLen="2" name="Country code" entity="printjob" id="PJTargetCountry" available=" pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ConstantTrue" varLen="0" name="True (constant)" entity="printjob" id="PJConstantTrue" available="

pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ConstantFalse" varLen="0" name="False (constant)" entity="printjob" id="PJConstantFalse" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ConstantZero" varLen="0" name="Zero (constant)" entity="printjob" id="PJConstantZero" available=" pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ConstantStringNull" varLen="1" name="Character 0 (constant)" entity="printjob" id=" PJConstantStringNull" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ColorModel" varLen="0" name="Color model code" entity="printjob" id="PJColorModel" available=" pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DuplexPrint" varLen="0" name="Duplexing print enabled" entity="printjob" id="PJDuplexPrint" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EmitterCode" varLen="0" name="Emitter code" entity="printjob" id="PJEmitterCode" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileExtension" varLen="10" name="Spoolfile extension (without dot)." entity="printjob" id=" PJSpoolfileExtension" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotId" varLen="256" name="External lot identifier" entity="printjob" id="PJLotId" available=" pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="JobId" varLen="256" name="External job identifier" entity="printjob" id="PJJobId" available=" pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SerializerId" varLen="50" name="External serializer identifier" entity="printjob" id=" PJSerializerId" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FileManagementId" varLen="50" name="External file management identifier" entity="printjob" id=" PJFileManagementId" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="OverprintId1" varLen="50" name="External overprint layer 1 identifier" entity="printjob" id=" PJOverprintId1" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="OverprintId2" varLen="50" name="External overprint layer 2 identifier" entity="printjob" id=" PJOverprintId2" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="OverprintId3" varLen="50" name="External overprint layer 3 identifier" entity="printjob" id=" PJOverprintId3" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="OverprintId4" varLen="50" name="External overprint layer 4 identifier" entity="printjob" id=" PJOverprintId4" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField1" varLen="10240" name="External custom field 1" entity="printjob" id=" PJePublishCustomField1" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField2" varLen="10240" name="External custom field 2" entity="printjob" id=" PJePublishCustomField2" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField3" varLen="10240" name="External custom field 3" entity="printjob" id=" PJePublishCustomField3" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField4" varLen="10240" name="External custom field 4" entity="printjob" id=" PJePublishCustomField4" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField5" varLen="10240" name="External custom field 5" entity="printjob" id="

PJePublishCustomField5" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField6" varLen="10240" name="External custom field 6" entity="printjob" id=" PJePublishCustomField6" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField7" varLen="10240" name="External custom field 7" entity="printjob" id=" PJePublishCustomField7" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField8" varLen="10240" name="External custom field 8" entity="printjob" id=" PJePublishCustomField8" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField9" varLen="10240" name="External custom field 9" entity="printjob" id=" PJePublishCustomField9" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ePublishCustomField10" varLen="10240" name="External custom field 10" entity="printjob" id=" PJePublishCustomField10" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="StartTimestamp" varLen="14" name="Process-start timestamp" entity="printjob" id=" PJStartTimestamp" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EndTimestamp" varLen="14" name="Process-end timestamp" entity="printjob" id="PJEndTimestamp" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DataFullFileName" varLen="256" name="Input data full filename" entity="printjob" id=" PJDataFullFileName" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DataFileName" varLen="256" name="Input data filename" entity="printjob" id="PJDataFileName" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Multispoolset" varLen="0" name="Multispoolset enabled" entity="printjob" id="PJMultiSpoolSet" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="AbsPath" varLen="256" name="Absolute output path" entity="printjob" id="PJAbsOutputPath" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalLots" varLen="0" name="Total lots" entity="printjob" id="PJTotalLots" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSpoolsets" varLen="0" name="Total spoolsets" entity="printjob" id="PJTotalSpoolsets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfilesCounter" varLen="0" name="Spoolfiles counter" entity="printjob" id=" PJSpoolfilesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentsCounter" varLen="0" name="Shipments counter" entity="printjob" id="PJDocumentsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field type="number" varLen="0" id="PJTemplatesCounter" entity="printjob" varName="TemplatesCounter" name=" Documents counter" createInstance="none" available="post"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="printjob" id="PJEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentsInErrorCounter" varLen="0" name="Shipments discarded counter" entity="printjob" id=" PJDocumentsInErrorCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplatesInErrorCounter" varLen="0" name="Documents discarded counter" entity="printjob" id=" PJTemplatesInErrorCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="printjob" id="

PJPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="printjob" id=" PJPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="printjob" id=" PJFillPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="printjob" id=" PJFillSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="printjob" id=" PJCoverPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="printjob" id=" PJCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="printjob" id="PJPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="printjob" id="PJSheetsCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="printjob" id="PJPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="printjob" id="PJSheetsCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="printjob" id="PJPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="printjob" id="PJSheetsCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="printjob" id="PJPagesCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="printjob" id="PJSheetsCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IndexesAbsPath" varLen="256" name="Indexes absolute path" entity="printjob" id=" PJIndexesAbsPath" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IndexesRelPath" varLen="256" name="Indexes relative path" entity="printjob" id=" PJIndexesRelPath" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FileName" varLen="256" name="Index filename" entity="printjob" id="PJIndexFileName" available=" pre" createInstance="index" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FullFileName" varLen="256" name="Index full filename" entity="printjob" id="PJIndexFullFileName" available="pre" createInstance="index" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="RecsCount" varLen="0" name="Index records counter" entity="printjob" id="PJIndexRecsCount" available="pre" createInstance="index" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="printjob" id="PJPersonCoverExtraPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets

counter" entity="printjob" id="PJPersCoverExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;cover pages counter" entity=" printjob" id="PJPersonalizeCoverPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity=" printjob" id="PJPersCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="printjob" id=" PJExtraPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="printjob" id=" PJExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="1PagesEnvelopesCounter" varLen="0" name="One-page envelopes counter" entity="printjob" id=" PJ1PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="2PagesEnvelopesCounter" varLen="0" name="Two-pages envelopes counter" entity="printjob" id=" PJ2PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="3PagesEnvelopesCounter" varLen="0" name="Three-pages envelopes counter" entity="printjob" id=" PJ3PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="4PagesEnvelopesCounter" varLen="0" name="Four-pages envelopes counter" entity="printjob" id=" PJ4PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="5PagesEnvelopesCounter" varLen="0" name="Five-pages envelopes counter" entity="printjob" id=" PJ5PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="6PagesEnvelopesCounter" varLen="0" name="Six-pages envelopes counter" entity="printjob" id=" PJ6PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="7PagesEnvelopesCounter" varLen="0" name="Seven-pages envelopes counter" entity="printjob" id=" PJ7PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="8PagesEnvelopesCounter" varLen="0" name="Eight-pages envelopes counter" entity="printjob" id=" PJ8PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9PagesEnvelopesCounter" varLen="0" name="Nine-pages envelopes counter" entity="printjob" id=" PJ9PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9UpPagesEnvelopesCounter" varLen="0" name="More than nine-pages envelopes counter" entity=" printjob" id="PJ9UpPagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="1SheetsEnvelopesCounter" varLen="0" name="One-sheet envelopes counter" entity="printjob" id=" PJ1SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="2SheetsEnvelopesCounter" varLen="0" name="Two-sheets envelopes counter" entity="printjob" id=" PJ2SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="3SheetsEnvelopesCounter" varLen="0" name="Three-sheets envelopes counter" entity="printjob" id=" PJ3SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="4SheetsEnvelopesCounter" varLen="0" name="Four-sheets envelopes counter" entity="printjob" id=" PJ4SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="5SheetsEnvelopesCounter" varLen="0" name="Five-sheets envelopes counter" entity="printjob" id=" PJ5SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="6SheetsEnvelopesCounter" varLen="0" name="Six-sheets envelopes counter" entity="printjob" id="

PJ6SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="7SheetsEnvelopesCounter" varLen="0" name="Seven-sheets envelopes counter" entity="printjob" id=" PJ7SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="8SheetsEnvelopesCounter" varLen="0" name="Eight-sheets envelopes counter" entity="printjob" id=" PJ8SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9SheetsEnvelopesCounter" varLen="0" name="Nine-sheets envelopes counter" entity="printjob" id=" PJ9SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9UpSheetsEnvelopesCounter" varLen="0" name="More than nine-sheets envelopes counter" entity=" printjob" id="PJ9UpSheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="printjob" id="PJEnvelopesCounter_Insert1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="printjob" id="PJEnvelopesCounter_Insert2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="printjob" id="PJEnvelopesCounter_Insert3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="printjob" id="PJEnvelopesCounter_Insert4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="printjob" id=" PJSheetsCounter_Insert1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="printjob" id=" PJSheetsCounter_Insert2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="printjob" id=" PJSheetsCounter_Insert3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="printjob" id=" PJSheetsCounter_Insert4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Id" varLen="50" name="Id" entity="lot" id="LotId" available="pre" createInstance="lot" type=" string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentsInErrorCounter" varLen="0" name="Shipments discarded counter" entity="lot" id=" LotDocumentsInErrorCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplatesInErrorCounter" varLen="0" name="Documents discarded counter" entity="lot" id=" LotTemplatesInErrorCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Enveloper3BitsGroupNumber" varLen="0" name="MailSystem envelope counter (3 bits)" entity="lot" id="LotEnveloper3BitsGroupNumber" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Enveloper4BitsGroupNumber" varLen="0" name="MailSystem envelope counter (4 bits)" entity="lot" id="LotEnveloper4BitsGroupNumber" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Enveloper5BitsGroupNumber" varLen="0" name="MailSystem envelope counter (5 bits)" entity="lot" id="LotEnveloper5BitsGroupNumber" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Enveloper3BitsSequenceNumber" varLen="0" name="MailSystem sheet counter (3 bits)" entity="lot" id="LotEnveloper3BitsSeqNumber" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Enveloper4BitsSequenceNumber" varLen="0" name="MailSystem sheet counter (4 bits)" entity="lot"

id="LotEnveloper4BitsSeqNumber" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Enveloper5BitsSequenceNumber" varLen="0" name="MailSystem sheet counter (5 bits)" entity="lot" id="LotEnveloper5BitsSeqNumber" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Name" varLen="256" name="Name" entity="lot" id="LotName" available="pre" createInstance="lot" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="lot" id=" LotPagesCounter_PAGETAG1" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="lot" id=" LotSheetsCounter_PAGETAG1" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="lot" id=" LotPagesCounter_PAGETAG2" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="lot" id=" LotSheetsCounter_PAGETAG2" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="lot" id=" LotPagesCounter_PAGETAG3" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="lot" id=" LotSheetsCounter_PAGETAG3" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="lot" id=" LotPagesCounter_PAGETAG4" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="lot" id=" LotSheetsCounter_PAGETAG4" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="lot" id="LotEnvelopesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="lot" id=" LotPersonalizedPagesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="lot" id=" LotPersonalizedSheetsCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="lot" id="LotFillPagesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="lot" id="LotFillSheetsCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="lot" id="LotCoverPagesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="lot" id=" LotCoverSheetsCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="lot" id="LotPersCoverExtraPagesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="lot" id="LotPersCoverExtraSheetsCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;Cover pages counter" entity="

lot" id="LotPersCoverPagesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity=" lot" id="LotPersCoverSheetsCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="lot" id="LotExtraPagesCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="lot" id=" LotExtraSheetsCounter" available="post" createInstance="lot" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Id" varLen="50" name="Identifier" entity="spoolset" id="SSId" available="pre" createInstance=" spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentsInErrorCounter" varLen="0" name="Shipments discarded counter" entity="spoolset" id=" SSDocumentsInErrorCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplatesInErrorCounter" varLen="0" name="Documents discarded counter" entity="spoolset" id=" SSTemplatesInErrorCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotId" varLen="50" name="Lot identifier" entity="spoolset" id="SSLotId" available="pre" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="AbsPath" varLen="256" name="Absolute path" entity="spoolset" id="SSAbsPath" available="pre" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="RelPath" varLen="256" name="Relative path" entity="spoolset" id="SSRelPath" available="pre" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IndexesAbsPath" varLen="256" name="Indexes absolute path" entity="spoolset" id=" SSIndexesAbsPath" available="pre" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IndexesRelPath" varLen="256" name="Indexes relative path" entity="spoolset" id=" SSIndexesRelPath" available="pre" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FileName" varLen="256" name="Index fileName" entity="spoolset" id="SSIndexFileName" available=" pre" createInstance="index" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FullFileName" varLen="256" name="Index full filename" entity="spoolset" id="SSIndexFullFileName" available="pre" createInstance="index" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="RecsCount" varLen="0" name="Index records counter" entity="spoolset" id="SSIndexRecsCount" available="pre" createInstance="index" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CurrentSpoolfileIsOpen" varLen="0" name="Current spoolfile is open" entity="spoolset" id=" SFfileIsOpen" available="pre" createInstance="spoolset" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SplitResolution" varLen="10" name="Split resolution" entity="spoolset" id="SSSplitResolution" available="pre" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SplitPageGroupSize" varLen="0" name="Split pagegroup size" entity="spoolset" id=" SSSplitPageGroupSize" available="pre" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfilesCounter" varLen="0" name="Spoolfiles counter" entity="spoolset" id=" SSSpoolfilesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="spoolset" id="SSEnvelopesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="spoolset" id="

SSPersPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="spoolset" id=" SSPersSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="spoolset" id=" SSFillPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="spoolset" id=" SSFillSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="spoolset" id=" SSCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="spoolset" id=" SSCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="spoolset" id="SSPersCoverExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="spoolset" id="SSPersCoverExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity=" spoolset" id="SSPersCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;Cover pages counter" entity=" spoolset" id="SSPersCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="spoolset" id=" SSExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="spoolset" id=" SSExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="spoolset" id="SSPagesCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="spoolset" id="SSSheetsCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="spoolset" id="SSPagesCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="spoolset" id="SSSheetsCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="spoolset" id="SSPagesCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="spoolset" id="SSSheetsCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="spoolset" id="SSPagesCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="spoolset" id="SSSheetsCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="1PagesEnvelopesCounter" varLen="0" name="One-page envelopes counter" entity="spoolset" id="

SS1PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="2PagesEnvelopesCounter" varLen="0" name="Two-pages envelopes counter" entity="spoolset" id=" SS2PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="3PagesEnvelopesCounter" varLen="0" name="Three-pages envelopes counter" entity="spoolset" id=" SS3PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="4PagesEnvelopesCounter" varLen="0" name="Four-pages envelopes counter" entity="spoolset" id=" SS4PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="5PagesEnvelopesCounter" varLen="0" name="Five-pages envelopes counter" entity="spoolset" id=" SS5PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="6PagesEnvelopesCounter" varLen="0" name="Six-pages envelopes counter" entity="spoolset" id=" SS6PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="7PagesEnvelopesCounter" varLen="0" name="Seven-pages envelopes counter" entity="spoolset" id=" SS7PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="8PagesEnvelopesCounter" varLen="0" name="Eight-pages envelopes counter" entity="spoolset" id=" SS8PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9PagesEnvelopesCounter" varLen="0" name="Nine-pages envelopes counter" entity="spoolset" id=" SS9PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9UpPagesEnvelopesCounter" varLen="0" name="More than nine-pages envelopes counter" entity=" spoolset" id="SS9UpPagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="1SheetsEnvelopesCounter" varLen="0" name="One-sheet envelopes counter" entity="spoolset" id=" SS1SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="2SheetsEnvelopesCounter" varLen="0" name="Two-sheets envelopes counter" entity="spoolset" id=" SS2SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="3SheetsEnvelopesCounter" varLen="0" name="Three-sheets envelopes counter" entity="spoolset" id=" SS3SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="4SheetsEnvelopesCounter" varLen="0" name="Four-sheets envelopes counter" entity="spoolset" id=" SS4SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="5SheetsEnvelopesCounter" varLen="0" name="Five-sheets envelopes counter" entity="spoolset" id=" SS5SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="6SheetsEnvelopesCounter" varLen="0" name="Six-sheets envelopes counter" entity="spoolset" id=" SS6SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="7SheetsEnvelopesCounter" varLen="0" name="Seven-sheets envelopes counter" entity="spoolset" id=" SS7SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="8SheetsEnvelopesCounter" varLen="0" name="Eight-sheets envelopes counter" entity="spoolset" id=" SS8SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9SheetsEnvelopesCounter" varLen="0" name="Nine-sheets envelopes counter" entity="spoolset" id=" SS9SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9UpSheetsEnvelopesCounter" varLen="0" name="More than nine-sheets envelopes counter" entity=" spoolset" id="SS9UpSheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="HeaderSheetEnabled" varLen="0" name="Header sheet enabling flag" entity="spoolset" id="

HeaderSheetEnabled" available="pre" createInstance="spoolset" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TrailerSheetEnabled" varLen="0" name="Trailer sheet enabling flag" entity="spoolset" id=" TrailerSheetEnabled" available="pre" createInstance="spoolset" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="spoolset" id="SSEnvelopesCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="spoolset" id="SSEnvelopesCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="spoolset" id="SSEnvelopesCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="spoolset" id="SSEnvelopesCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="spoolset" id=" SSSheetsCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="spoolset" id=" SSSheetsCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="spoolset" id=" SSSheetsCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="spoolset" id=" SSSheetsCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field type="number" varLen="0" id="SSTemplatesCounter" entity="spoolset" varName="TemplatesCounter" name=" Documents counter" createInstance="spoolset" available="post"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FileName" varLen="256" name="Filename" entity="spoolfile" id="SFFileName" available="post" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FullFileName" varLen="256" name="full filename" entity="spoolfile" id="SFFullFileName" available="post" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="AbsPath" varLen="256" name="Absolute path" entity="spoolfile" id="SFSpoolfilesAbsPath" available="post" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="RelPath" varLen="256" name="Relative path" entity="spoolfile" id="SFSpoolfilesRelPath" available="post" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IndexesAbsPath" varLen="256" name="Indexes absolute path" entity="spoolfile" id=" SFIndexesAbsPath" available="post" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IndexesRelPath" varLen="256" name="Indexes relative path" entity="spoolfile" id=" SFIndexesRelPath" available="post" createInstance="spoolset" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FileName" varLen="256" name="Index filename" entity="spoolfile" id="SFIndexFileName" available=" post" createInstance="index" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FullFileName" varLen="256" name="Index full filename" entity="spoolfile" id=" SFIndexFullFileName" available="post" createInstance="index" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="RecsCount" varLen="0" name="Index records counter" entity="spoolfile" id="SFIndexRecsCount" available="post" createInstance="index" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="spoolfile" id="SFEnvelopesCounter"

available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentsCounter" varLen="0" name="Shipments counter" entity="spoolfile" id="SFDocumentsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplatesCounter" varLen="0" name="Documents counter" entity="spoolfile" id="SFTemplatesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="spoolfile" id=" SFPersonalizedPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="spoolfile" id=" SFPersonalizedSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="spoolfile" id=" SFFillPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="spoolfile" id=" SFFillSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="spoolfile" id=" SFCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="spoolfile" id=" SFCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="spoolfile" id="SFPagesCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity=" spoolfile" id="SFSheetsCounter_PAGETAG1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="spoolfile" id="SFPagesCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity=" spoolfile" id="SFSheetsCounter_PAGETAG2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="spoolfile" id="SFPagesCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity=" spoolfile" id="SFSheetsCounter_PAGETAG3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="spoolfile" id="SFPagesCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity=" spoolfile" id="SFSheetsCounter_PAGETAG4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="spoolfile" id="SFPersCoverExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="spoolfile" id="SFPersCoverExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;Cover pages counter" entity=" spoolfile" id="SFPersCoverPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;Cover sheets counter" entity="

spoolfile" id="SFPersCoverSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="spoolfile" id=" SFExtraPagesCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="spoolfile" id=" SFExtraSheetsCounter" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="1PagesEnvelopesCounter" varLen="0" name="One-page envelopes counter" entity="spoolfile" id=" SF1PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="2PagesEnvelopesCounter" varLen="0" name="Two-pages envelopes counter" entity="spoolfile" id=" SF2PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="3PagesEnvelopesCounter" varLen="0" name="Three-pages envelopes counter" entity="spoolfile" id=" SF3PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="4PagesEnvelopesCounter" varLen="0" name="Four-pages envelopes counter" entity="spoolfile" id=" SF4PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="5PagesEnvelopesCounter" varLen="0" name="Five-pages envelopes counter" entity="spoolfile" id=" SF5PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="6PagesEnvelopesCounter" varLen="0" name="Six-pages envelopes counter" entity="spoolfile" id=" SF6PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="7PagesEnvelopesCounter" varLen="0" name="Seven-pages envelopes counter" entity="spoolfile" id=" SF7PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="8PagesEnvelopesCounter" varLen="0" name="Eight-pages envelopes counter" entity="spoolfile" id=" SF8PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9PagesEnvelopesCounter" varLen="0" name="Nine-pages envelopes counter" entity="spoolfile" id=" SF9PagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9UpPagesEnvelopesCounter" varLen="0" name="More than nine-pages envelopes counter" entity=" spoolfile" id="SF9UpPagesEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="1SheetsEnvelopesCounter" varLen="0" name="One-sheet envelopes counter" entity="spoolfile" id=" SF1SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="2SheetsEnvelopesCounter" varLen="0" name="Two-sheets envelopes counter" entity="spoolfile" id=" SF2SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="3SheetsEnvelopesCounter" varLen="0" name="Three-sheets envelopes counter" entity="spoolfile" id=" SF3SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="4SheetsEnvelopesCounter" varLen="0" name="Four-sheets envelopes counter" entity="spoolfile" id=" SF4SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="5SheetsEnvelopesCounter" varLen="0" name="Five-sheets envelopes counter" entity="spoolfile" id=" SF5SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="6SheetsEnvelopesCounter" varLen="0" name="Six-sheets envelopes counter" entity="spoolfile" id=" SF6SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="7SheetsEnvelopesCounter" varLen="0" name="Seven-sheets envelopes counter" entity="spoolfile" id=" SF7SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="8SheetsEnvelopesCounter" varLen="0" name="Eight-sheets envelopes counter" entity="spoolfile" id="

SF8SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9SheetsEnvelopesCounter" varLen="0" name="Nine-sheets envelopes counter" entity="spoolfile" id=" SF9SheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="9UpSheetsEnvelopesCounter" varLen="0" name="More than nine-sheets envelopes counter" entity=" spoolfile" id="SF9UpSheetsEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="spoolfile" id="SFEnvelopesCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="spoolfile" id="SFEnvelopesCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="spoolfile" id="SFEnvelopesCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="spoolfile" id="SFEnvelopesCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="spoolfile" id=" SFSheetsCounter_Insert1" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="spoolfile" id=" SFSheetsCounter_Insert2" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="spoolfile" id=" SFSheetsCounter_Insert3" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="spoolfile" id=" SFSheetsCounter_Insert4" available="post" createInstance="spoolset" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="KilobytesDimension" varLen="0" name="The dimension of spoolfile in kB" entity="spoolfile" id=" SFkiloBytesDimension" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="MegaBytesDimension" varLen="0" name="The dimension of spoolfile in MB" entity="spoolfile" id=" SFMegaBytesDimension" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeSheetsCapacity" varLen="0" name="Envelope sheets capacity" entity="document" id=" DOEnvelopeSheetsCapacity" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="InError" varLen="0" name="Discarded shipment" entity="document" id="DOInError" available="post" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ShipmentErrorCode" varLen="4" name="Shipment discarded error code" entity="document" id=" DOErrorCode" available="post" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ShipmentErrorMessage" varLen="1024" name="Shipment discarded error message" entity="document" id="DOErrorMessage" available="post" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FirstEnvelopePersonalizedSheetsCapacity" varLen="0" name="First envelope personalized sheets capacity" entity="document" id="DOFirstEnvPersSheetsCapacity" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="AllButFirstEnvelopePersonalizedSheetsCapacity" varLen="0" name="All but first envelope personalized sheets capacity" entity="document" id="DOAllButFirstEnvPersSheetsCap" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Multienvelopes" varLen="0" name="Multienvelopes enabled" entity="document" id="DOMultienvelopes" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="UseCover" varLen="0" name="Cover enabled" entity="document" id="DOUseCover" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverOnFirstEnvelope" varLen="0" name="First envelope cover enabled" entity="document" id=" DOCoverOnFirstEnvelope" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PrintjobPos" varLen="0" name="Printjob position" entity="document" id="DOPrintjobPos" available=" pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DatafileStartPos" varLen="0" name="Datafile start position" entity="document" id=" DODatafileStartPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DatafileEndPos" varLen="0" name="Datafile end position" entity="document" id="DODatafileEndPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Timestamp" varLen="14" name="Timestamp" entity="document" id="DOTimestamp" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalEnvelopes" varLen="0" name="Total envelopes" entity="document" id="DOTotalEnvelopes" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalTemplates" varLen="0" name="Total documents" entity="document" id="DOTotalTemplates" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter" varLen="0" name="Envelopes counter" entity="document" id="DOEnvelopesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplatesCounter" varLen="0" name="Documents counter" entity="document" id="DOTemplatesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedPages" varLen="0" name="Total personalized pages" entity="document" id=" DOTotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedSheets" varLen="0" name="Total personalized sheets" entity="document" id=" DOTotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFillPages" varLen="0" name="Total blank pages" entity="document" id="DOTotalFillPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFillSheets" varLen="0" name="Total blank sheets" entity="document" id="DOTotalFillSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalCoverPages" varLen="0" name="Total cover pages" entity="document" id="DOTotalCoverPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalCoverSheets" varLen="0" name="Total cover sheets" entity="document" id="DOTotalCoverSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFirstEnvelopePersonalizedPages" varLen="0" name="Total first envelope personalized pages" entity="document" id="DOTotalFirstEnvelopePersPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFirstEnvelopePersonalizedSheets" varLen="0" name="Total first envelope personalized sheets" entity="document" id="DOTotalFirstEnvelopePersSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalInterEnvelopePersonalizedPages" varLen="0" name="Total inter-envelope personalized pages" entity="document" id="DOTotalInterEnvelopePersPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalInterEnvelopePersonalizedSheets" varLen="0" name="Total inter-envelope personalized sheets" entity="document" id="DOTotalInterEnvelopePersSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalLastEnvelopePersonalizedPages" varLen="0" name="Total last envelope personalized pages" entity="document" id="DOTotalLastEnvelopePersPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalLastEnvelopePersonalizedSheets" varLen="0" name="Total last envelope personalized sheets" entity="document" id="DOTotalLastEnvelopePersSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFirstEnvelopeCoverPages" varLen="0" name="Total first envelope cover pages" entity=" document" id="DOTotalFirstEnvelopeCoverPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFirstEnvelopeCoverSheets" varLen="0" name="Total first envelope cover sheets" entity=" document" id="DOTotalFirstEnvCoverSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalAllButFirstEnvelopeCoverPages" varLen="0" name="Total all but first envelope cover pages" entity="document" id="DOTotalAllButFirstEnvCovPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalAllButFirstEnvelopeCoverSheets" varLen="0" name="Total all but first envelope cover sheets" entity="document" id="DOTotalAllButFirstEnvCovSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFirstEnvelopeExtraPages" varLen="0" name="Total first envelope extra pages" entity=" document" id="DOTotalFirstEnvelopeExtraPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFirstEnvelopeExtraSheets" varLen="0" name="Total first envelope extra sheets" entity=" document" id="DOTotalFirstEnvExtraSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalAllEnvelopesExtraPages" varLen="0" name="Total all envelopes extra pages" entity="document" id="DOTotalAllEnvExtraPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalAllEnvelopesExtraSheets" varLen="0" name="Total all envelopes extra sheets" entity=" document" id="DOTotalAllEnvExtraSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPages_PAGETAG1" varLen="0" name="Total pages with page attribute 1" entity="document" id=" DOTotalPages_PAGETAG1" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_PAGETAG1" varLen="0" name="Total sheets with page attribute 1" entity="document" id=" DOTotalSheets_PAGETAG1" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPages_PAGETAG2" varLen="0" name="Total pages with page attribute 2" entity="document" id=" DOTotalPages_PAGETAG2" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_PAGETAG2" varLen="0" name="Total sheets with page attribute 2" entity="document" id=" DOTotalSheets_PAGETAG2" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPages_PAGETAG3" varLen="0" name="Total pages with page attribute 3" entity="document" id=" DOTotalPages_PAGETAG3" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_PAGETAG3" varLen="0" name="Total sheets with page attribute 3" entity="document" id=" DOTotalSheets_PAGETAG3" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPages_PAGETAG4" varLen="0" name="Total pages with page attribute 4" entity="document" id=" DOTotalPages_PAGETAG4" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_PAGETAG4" varLen="0" name="Total sheets with page attribute 4" entity="document" id=" DOTotalSheets_PAGETAG4" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="document" id="DOPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="document" id="DOSheetsCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="document" id="DOPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="document" id="DOSheetsCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="document" id="DOPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="document" id="DOSheetsCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="document" id="DOPagesCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="document" id="DOSheetsCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="document" id=" DOPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="document" id=" DOPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="document" id=" DOFillPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="document" id=" DOFillSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="document" id=" DOCoverPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="document" id=" DOCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverExtraPages" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra pages" entity="document" id="DOTotalPersCoverExtraPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverExtraSheets" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra sheets" entity="document" id="DOTotalPersCoverExtraSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverPages" varLen="0" name="Total personalized&amp;amp;cover pages" entity=" document" id="DOTotalPersCoverPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverSheets" varLen="0" name="Total personalized&amp;amp;cover sheets" entity=" document" id="DOTotalPersCoverSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalExtraPages" varLen="0" name="Total extra pages" entity="document" id="DOTotalExtraPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalExtraSheets" varLen="0" name="Total extra sheets" entity="document" id="DOTotalExtraSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="document" id="DOPersoCoverExtraPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="document" id="DOPersCoverExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;cover pages counter" entity=" document" id="DOPersCoverPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;cover sheets counter" entity=" document" id="DOPersCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="document" id=" DOExtraPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="document" id=" DOExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileSegmentCounter" varLen="0" name="Document spoolfiles counter" entity="document" id=" DOSegmentCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert1" varLen="0" name="Envelopes counter with insert 1" entity="document" id="DOEnvelopesCounter_Insert1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert2" varLen="0" name="Envelopes counter with insert 2" entity="document" id="DOEnvelopesCounter_Insert2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert3" varLen="0" name="Envelopes counter with insert 3" entity="document" id="DOEnvelopesCounter_Insert3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopesCounter_Insert4" varLen="0" name="Envelopes counter with insert 4" entity="document" id="DOEnvelopesCounter_Insert4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalEnvelopes_Insert1" varLen="0" name="Total envelopes counter with insert 1" entity=" document" id="DOTotalEnvelopes_Insert1" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalEnvelopes_Insert2" varLen="0" name="Total envelopes counter with insert 2" entity=" document" id="DOTotalEnvelopes_Insert2" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalEnvelopes_Insert3" varLen="0" name="Total envelopes counter with insert 3" entity=" document" id="DOTotalEnvelopes_Insert3" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalEnvelopes_Insert4" varLen="0" name="Total envelopes counter with insert 4" entity=" document" id="DOTotalEnvelopes_Insert4" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert1" varLen="0" name="Insert 1 sheets counter" entity="document" id=" DOSheetsCounter_Insert1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert2" varLen="0" name="Insert 2 sheets counter" entity="document" id=" DOSheetsCounter_Insert2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert3" varLen="0" name="Insert 3 sheets counter" entity="document" id=" DOSheetsCounter_Insert3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_Insert4" varLen="0" name="Insert 4 sheets counter" entity="document" id=" DOSheetsCounter_Insert4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert1" varLen="0" name="Total sheets insert 1" entity="document" id=" DOTotalSheets_Insert1" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert2" varLen="0" name="Total sheets insert 2" entity="document" id=" DOTotalSheets_Insert2" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert3" varLen="0" name="Total sheets insert 3" entity="document" id=" DOTotalSheets_Insert3" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert4" varLen="0" name="Total sheets insert 4" entity="document" id=" DOTotalSheets_Insert4" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeFirstPagePos" varLen="0" name="Envelope first page position" entity="template" id=" TEEnvelopeFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="InError" varLen="0" name="Discarded document" entity="template" id="TEInError" available="post" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentErrorCode" varLen="4" name="Document discarded error code" entity="template" id=" TEErrorCode" available="post" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentErrorMessage" varLen="1024" name="Document discarded error message" entity="template" id="TEErrorMessage" available="post" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeFirstSheetPos" varLen="0" name="Envelope first sheet position" entity="template" id=" TEEnvelopeFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLastPagePos" varLen="0" name="Envelope last page position" entity="template" id=" TEEnvelopeLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLastSheetPos" varLen="0" name="Envelope last sheet position" entity="template" id=" TEEnvelopeLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotPos" varLen="0" name="Lot position" entity="template" id="TELotPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotFirstPagePos" varLen="0" name="Envelope lot first page position" entity="template" id="TEEnvLotFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotFirstSheetPos" varLen="0" name="Envelope lot first sheet position" entity="template" id="TEEnvLotFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotLastPagePos" varLen="0" name="Envelope lot last page position" entity="template" id=" TEEnvLotLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotLastSheetPos" varLen="0" name="Envelope lot last sheet position" entity="template" id="TEEnvLotLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstPagePos" varLen="0" name="Lot first page position" entity="template" id=" TELotFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstSheetPos" varLen="0" name="Lot first sheet position" entity="template" id=" TELotFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotLastPagePos" varLen="0" name="Lot last page position" entity="template" id="TELotLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotLastSheetPos" varLen="0" name="Lot last sheet position" entity="template" id=" TELotLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetPos" varLen="0" name="Spoolset position" entity="template" id="TESpoolsetPos" available=" pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstPagePos" varLen="0" name="Spoolset first page position" entity="template" id=" TESpoolsetFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstSheetPos" varLen="0" name="Spoolset first sheet position" entity="template" id=" TESpoolsetFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastPagePos" varLen="0" name="Spoolset last page position" entity="template" id=" TESpoolsetLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastSheetPos" varLen="0" name="Spoolset last sheet position" entity="template" id=" TESpoolsetLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstPagePos" varLen="0" name="Spoolfile first page position" entity="template" id=" TESpoolfileFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstSheetPos" varLen="0" name="Spoolfile first sheet position" entity="template" id=" TESpoolfileFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastPagePos" varLen="0" name="Spoolfile last page position" entity="template" id=" TESpoolfileLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastSheetPos" varLen="0" name="Spoolfile last sheet position" entity="template" id=" TESpoolfileLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeFirstEmptyPagePos" varLen="0" name="Envelope first blank page position" entity=" template" id="TEEnvelopeFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeFirstEmptySheetPos" varLen="0" name="Envelope first blank sheet position" entity=" template" id="TEEnvelopeFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLastEmptyPagePos" varLen="0" name="Envelope last blank page position" entity="template" id="TEEnvelopeLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLastEmptySheetPos" varLen="0" name="Envelope last blank sheet position" entity=" template" id="TEEnvelopeLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotFirstEmptyPagePos" varLen="0" name="Envelope lot first blank page position" entity=" template" id="TEEnvLotFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotFirstEmptySheetPos" varLen="0" name="Envelope lot first blank sheet position" entity=" template" id="TEEnvLotFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotLastEmptyPagePos" varLen="0" name="Envelope lot last blank page position" entity=" template" id="TEEnvLotLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotLastEmptySheetPos" varLen="0" name="Envelope lot last blank sheet position" entity=" template" id="TEEnvLotLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstEmptyPagePos" varLen="0" name="Lot first blank page position" entity="template" id=" TELotFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstEmptySheetPos" varLen="0" name="Lot first blank sheet position" entity="template" id=" TELotFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotLastEmptyPagePos" varLen="0" name="Lot last blank page position" entity="template" id=" TELotLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotLastEmptySheetPos" varLen="0" name="Lot last blank sheet position" entity="template" id=" TELotLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstEmptyPagePos" varLen="0" name="Spoolset first blank page position" entity=" template" id="TESpoolsetFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstEmptySheetPos" varLen="0" name="Spoolset first blank sheet position" entity=" template" id="TESpoolsetFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastEmptyPagePos" varLen="0" name="Spoolset last blank page position" entity="template" id="TESpoolsetLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastEmptySheetPos" varLen="0" name="Spoolset last blank sheet position" entity=" template" id="TESpoolsetLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstEmptyPagePos" varLen="0" name="Spoolfile first blank page position" entity=" template" id="TESpoolfileFirstEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstEmptySheetPos" varLen="0" name="Spoolfile first blank sheet position" entity=" template" id="TESpoolfileFirstEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastEmptyPagePos" varLen="0" name="Spoolfile last blank page position" entity=" template" id="TESpoolfileLastEmptyPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastEmptySheetPos" varLen="0" name="Spoolfile last blank sheet position" entity=" template" id="TESpoolfileLastEmptySheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LastPageisFill" varLen="0" name="Last page is blank" entity="template" id="TELastPageisEmpty" available="post" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedPages" varLen="0" name="Document total personalized pages" entity="template" id="TETotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedPagesNoFill" varLen="0" name="Document total personalized pages without blanks" entity="template" id="TETotalPersonalizedPagesNoFill" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedSheets" varLen="0" name="Document total personalized sheets" entity="template" id="TETotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedSheetsNoFill" varLen="0" name="Document total personalized sheets without blanks" entity="template" id="TETotalPersonalizedSheetsNoFill" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPageSections" name="Document total page sections" varLen="0" entity="template" id=" TETotalPageSections" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PageSectionsCounter" name="Page sections counter" varLen="0" entity="template" id=" TEPageSectionsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CurrentPersonalizedPage" varLen="0" name="Document current personalized page" entity="template" id="TECurrentPersonalizedPage" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CurrentSheet" varLen="0" name="Document current sheet" entity="template" id="TECurrentSheet" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotId" varLen="50" name="Lot identifier" entity="envelope" id="ENLotId" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetId" varLen="50" name="Spoolset identifier" entity="envelope" id="ENSpoolsetId" available="pre" createInstance="none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentPos" varLen="0" name="Shipment position" entity="envelope" id="ENDocumentPos" available=" pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentFirstPagePos" varLen="0" name="Shipment first page position" entity="envelope" id=" ENDocumentFirstPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentFirstSheetPos" varLen="0" name="Shipment first sheet position" entity="envelope" id=" ENDocumentFirstSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentLastPagePos" varLen="0" name="Shipment last page position" entity="envelope" id=" ENDocumentLastPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentLastSheetPos" varLen="0" name="Shipment last sheet position" entity="envelope" id=" ENDocumentLastSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstPagePos" varLen="0" name="Lot first page position" entity="envelope" id=" ENLotFirstPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstSheetPos" varLen="0" name="Lot first sheet position" entity="envelope" id=" ENLotFirstSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotLastPagePos" varLen="0" name="Lot last page position" entity="envelope" id="ENLotLastPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotLastSheetPos" varLen="0" name="Lot last sheet position" entity="envelope" id=" ENLotLastSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstPagePos" varLen="0" name="Spoolset first page position" entity="envelope" id=" ENSpoolsetFirstPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstSheetPos" varLen="0" name="Spoolset first sheet position" entity="envelope" id=" ENSpoolsetFirstSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastPagePos" varLen="0" name="Spoolset last page position" entity="envelope" id=" ENSpoolsetLastPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastSheetPos" varLen="0" name="Spoolset last sheet position" entity="envelope" id=" ENSpoolsetLastSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstPagePos" varLen="0" name="Spoolfile first page position" entity="envelope" id=" ENSpoolfileFirstPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstSheetPos" varLen="0" name="Spoolfile first sheet position" entity="envelope" id=" ENSpoolfileFirstSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastPagePos" varLen="0" name="Spoolfile last page position" entity="envelope" id=" ENSpoolfileLastPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastSheetPos" varLen="0" name="Spoolfile last sheet position" entity="envelope" id=" ENSpoolfileLastSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedPages" varLen="0" name="Total personalized pages" entity="envelope" id=" ENTotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedSheets" varLen="0" name="Total personalized sheets" entity="envelope" id=" ENTotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFillPages" varLen="0" name="Total blank pages" entity="envelope" id="ENTotalFillPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalFillSheets" varLen="0" name="Total blank sheets" entity="envelope" id="ENTotalFillSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalCoverPages" varLen="0" name="Total cover pages" entity="envelope" id="ENTotalCoverPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalCoverSheets" varLen="0" name="Total cover sheets" entity="envelope" id="ENTotalCoverSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalExtraPages" varLen="0" name="Total extra pages" entity="envelope" id="ENTotalExtraPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalExtraSheets" varLen="0" name="Total extra sheets" entity="envelope" id="ENTotalExtraSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="envelope" id="ENPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG1" varLen="0" name="Sheets counter with page attribute 1" entity="envelope" id="ENSheetsCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="envelope" id="ENPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG2" varLen="0" name="Sheets counter with page attribute 2" entity="envelope" id="ENSheetsCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="envelope" id="ENPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG3" varLen="0" name="Sheets counter with page attribute 3" entity="envelope" id="ENSheetsCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG4" varLen="0" name="Pages counter with page attribute 4" entity="envelope" id="ENPagesCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SheetsCounter_PAGETAG4" varLen="0" name="Sheets counter with page attribute 4" entity="envelope" id="ENSheetsCounter_PAGETAG4" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="envelope" id=" ENPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="envelope" id=" ENPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="envelope" id=" ENFillPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="envelope" id=" ENFillSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverPagesCounter" varLen="0" name="Cover pages counter" entity="envelope" id=" ENCoverPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="CoverSheetsCounter" varLen="0" name="Cover sheets counter" entity="envelope" id=" ENCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverExtraPages" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra pages" entity="envelope" id="ENTotalPersCoverExtraPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverExtraSheets" varLen="0" name="Total personalized&amp;amp;cover&amp;amp;extra sheets" entity="envelope" id="ENTotalPersCoverExtraSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverPages" varLen="0" name="Total personalized&amp;amp;cover pages" entity=" envelope" id="ENTotalPersCoverPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedCoverSheets" varLen="0" name="Total personalized&amp;amp;cover sheets" entity=" envelope" id="ENTotalPersCoverSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraPagesCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra pages counter" entity="envelope" id="ENPersCoverExtraPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverExtraSheetsCounter" varLen="0" name="Personalized&amp;amp;cover&amp;amp;extra sheets counter" entity="envelope" id="ENPersCoverExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverPagesCounter" varLen="0" name="Personalized&amp;amp;cover pages counter" entity=" envelope" id="ENPersCoverPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedCoverSheetsCounter" varLen="0" name="Personalized&amp;amp;cover sheets counter" entity=" envelope" id="ENPersCoverSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraPagesCounter" varLen="0" name="Extra pages counter" entity="envelope" id=" ENExtraPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="ExtraSheetsCounter" varLen="0" name="Extra sheets counter" entity="envelope" id=" ENExtraSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileSegmentCounter" varLen="0" name="Envelope spoolfiles counter" entity="envelope" id=" ENSegmentCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert1" varLen="0" name="Total sheets insert 1" entity="envelope" id=" ENTotalSheets_Insert1" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert2" varLen="0" name="Total sheets insert 2" entity="envelope" id=" ENTotalSheets_Insert2" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert3" varLen="0" name="Total sheets insert 3" entity="envelope" id=" ENTotalSheets_Insert3" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalSheets_Insert4" varLen="0" name="Total sheets insert 4" entity="envelope" id=" ENTotalSheets_Insert4" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Name" name="Name" varLen="256" entity="section" id="PSName" available="pre" createInstance=" none" type="string"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPages" name="Total Pages" varLen="0" entity="section" id="PSTotalPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplateFirstPagePos" name="Document first page position" varLen="0" entity="section" id=" PSTemplateFirstPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TemplateLastPagePos" name="Document last page position" varLen="0" entity="section" id=" PSTemplateLastPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentFirstPagePos" name="Shipment first page position" varLen="0" entity="section" id=" PSDocumentFirstPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentLastPagePos" name="Shipment last page position" varLen="0" entity="section" id=" PSDocumentLastPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeFirstPagePos" name="Envelope first page position" varLen="0" entity="section" id=" PSEnvelopeFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeFirstSheetPos" name="Envelope first sheet position" varLen="0" entity="section" id=" PSEnvelopeFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstPagePos" name="Lot first page position" varLen="0" entity="section" id=" PSLotFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotFirstSheetPos" name="Lot first sheet position" varLen="0" entity="section" id=" PSLotFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstPagePos" name="Spoolset first page position" varLen="0" entity="section" id=" PSSpoolsetFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetFirstSheetPos" name="Spoolset first sheet position" varLen="0" entity="section" id=" PSSpoolsetFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstPagePos" name="Spoolfile first page position" varLen="0" entity="section" id=" PSSpoolfileFirstPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileFirstSheetPos" name="Spoolfile first sheet position" varLen="0" entity="section" id=" PSSpoolfileFirstSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedPages" name="Total personalized pages" varLen="0" entity="section" id=" PSTotalPersonalizedPages" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedPagesNoFill" name="Document total personalized pages without blanks" varLen="0" entity="section" id="PSTotalPersonalizedPagesNoFill" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedSheets" name="Document total personalized sheets" varLen="0" entity="section" id="PSTotalPersonalizedSheets" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="TotalPersonalizedSheetsNoFill" name="Document total personalized sheets without blanks" varLen=" 0" entity="section" id="PSTotalPersonalizedSheetsNoFill" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;omsf:field varName="EnvelopeLastPagePos" varLen="0" name="Envelope last page position" entity="section" id=" PSEnvelopeLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLastSheetPos" varLen="0" name="Envelope last sheet position" entity="section" id=" PSEnvelopeLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotLastPagePos" varLen="0" name="Envelope lot last page position" entity="section" id=" PSEnvLotLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeLotLastSheetPos" varLen="0" name="Envelope lot last sheet position" entity="section" id="PSEnvLotLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastPagePos" varLen="0" name="Spoolset last page position" entity="section" id=" PSSpoolsetLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetLastSheetPos" varLen="0" name="Spoolset last sheet position" entity="section" id=" PSSpoolsetLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastPagePos" varLen="0" name="Spoolfile last page position" entity="section" id=" PSSpoolfileLastPagePos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileLastSheetPos" varLen="0" name="Spoolfile last sheet position" entity="section" id=" PSSpoolfileLastSheetPos" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedPagesCounter" varLen="0" name="Personalized pages counter" entity="section" id=" PSJPersonalizedPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PersonalizedSheetsCounter" varLen="0" name="Personalized sheets counter" entity="section" id=" PSPersonalizedSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillPagesCounter" varLen="0" name="Blank pages counter" entity="section" id=" PSFillPagesCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="FillSheetsCounter" varLen="0" name="Blank sheets counter" entity="section" id="

PSFillSheetsCounter" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG1" varLen="0" name="Pages counter with page attribute 1" entity="section" id="PSPagesCounter_PAGETAG1" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG2" varLen="0" name="Pages counter with page attribute 2" entity="section" id="PSPagesCounter_PAGETAG2" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="PagesCounter_PAGETAG3" varLen="0" name="Pages counter with page attribute 3" entity="section" id="PSPagesCounter_PAGETAG3" available="post" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isFront" varLen="0" name="is Front" entity="page" id="PGisFront" available="pre" createInstance=" none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isBack" varLen="0" name="is Back" entity="page" id="PGisBack" available="pre" createInstance=" none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isFill" varLen="0" name="is Blank" entity="page" id="PGisFill" available="pre" createInstance=" none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isCover" varLen="0" name="is Cover" entity="page" id="PGisCover" available="pre" createInstance=" none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isPAGETAG1" varLen="0" name="has page attribute 1" entity="page" id="PGisPAGETAG1" available=" pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isPAGETAG2" varLen="0" name="has page attribute 2" entity="page" id="PGisPAGETAG2" available=" pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isPAGETAG3" varLen="0" name="has page attribute 3" entity="page" id="PGisPAGETAG3" available=" pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="isPAGETAG4" varLen="0" name="has page attribute 4" entity="page" id="PGisPAGETAG4" available=" pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotPagePos" varLen="0" name="Lot page position" entity="page" id="PGLotPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="LotSheetPos" varLen="0" name="Lot sheet position" entity="page" id="PGLotSheetPos" available=" pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopePagePos" varLen="0" name="Envelope page position" entity="page" id="PGEnvelopePagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeSheetPos" varLen="0" name="Envelope sheet position" entity="page" id=" PGEnvelopeSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentPagePos" varLen="0" name="Shipment page position" entity="page" id="PGDocumentPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="DocumentSheetPos" varLen="0" name="Shipment sheet position" entity="page" id=" PGDocumentSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfilePagePos" varLen="0" name="Spoolfile page position" entity="page" id=" PGSpoolfilePagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolfileSheetPos" varLen="0" name="Spoolfile sheet position" entity="page" id=" PGSpoolfileSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetPagePos" varLen="0" name="Spoolset page position" entity="page" id="PGSpoolsetPagePos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="SpoolsetSheetPos" varLen="0" name="Spoolset sheet position" entity="page" id=" PGSpoolsetSheetPos" available="pre" createInstance="none" type="number"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsFirstPage" varLen="0" name="Is first page of envelope" entity="page" id=" PGEnvelopeIsFirstPage" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsFirstSheet" varLen="0" name="Is first sheet of envelope" entity="page" id=" PGEnvelopeIsFirstSheet" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsNotFirstPage" varLen="0" name="Is not first page of envelope" entity="page" id=" PGEnvelopeIsNotFirstPage" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsNotFirstSheet" varLen="0" name="Is not first sheet of envelope" entity="page" id=" PGEnvelopeIsNotFirstSheet" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsLastPage" varLen="0" name="Is last page of envelope" entity="page" id=" PGEnvelopeIsLastPage" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsLastSheet" varLen="0" name="Is last sheet of envelope" entity="page" id=" PGEnvelopeIsLastSheet" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsNotLastPage" varLen="0" name="Is not last page of envelope" entity="page" id=" PGEnvelopeIsNotLastPage" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="EnvelopeIsNotLastSheet" varLen="0" name="Is not last sheet of envelope" entity="page" id=" PGEnvelopeIsNotLastSheet" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr3BitsGroupNumberBit0" varLen="0" name="MailSystem envelope counter

(3

bits)

bit

0"

entity="

page" id="PGOmr3BitsGroupNumberBit0" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr3BitsGroupNumberBit1" varLen="0" name="MailSystem envelope counter

(3

bits)

bit

1"

entity="

page" id="PGOmr3BitsGroupNumberBit1" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr3BitsGroupNumberBit2" varLen="0" name="MailSystem envelope counter

(3

bits)

bit

2"

entity="

page" id="PGOmr3BitsGroupNumberBit2" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsGroupNumberBit0" varLen="0" name="MailSystem envelope counter

(4

bits)

bit

0"

entity="

page" id="PGOmr4BitsGroupNumberBit0" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsGroupNumberBit1" varLen="0" name="MailSystem envelope counter

(4

bits)

bit

1"

entity="

page" id="PGOmr4BitsGroupNumberBit1" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsGroupNumberBit2" varLen="0" name="MailSystem envelope counter

(4

bits)

bit

2"

entity="

page" id="PGOmr4BitsGroupNumberBit2" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsGroupNumberBit3" varLen="0" name="MailSystem envelope counter

(4

bits)

bit

3"

entity="

page" id="PGOmr4BitsGroupNumberBit3" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsGroupNumberBit0" varLen="0" name="MailSystem envelope counter

(5

bits)

bit

0"

entity="

page" id="PGOmr5BitsGroupNumberBit0" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsGroupNumberBit1" varLen="0" name="MailSystem envelope counter

(5

bits)

bit

1"

entity="

page" id="PGOmr5BitsGroupNumberBit1" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsGroupNumberBit2" varLen="0" name="MailSystem envelope counter

(5

bits)

bit

2"

entity="

page" id="PGOmr5BitsGroupNumberBit2" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsGroupNumberBit3" varLen="0" name="MailSystem envelope counter

(5

bits)

bit

3"

entity="

page" id="PGOmr5BitsGroupNumberBit3" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsGroupNumberBit4" varLen="0" name="MailSystem envelope counter

(5

bits)

bit

4"

entity="

page" id="PGOmr5BitsGroupNumberBit4" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr3BitsSequenceNumberBit0" varLen="0" name="MailSystem sheet counter

(3

bits)

bit

0"

entity="

page" id="PGOmr3BitsSequenceNumberBit0" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr3BitsSequenceNumberBit1" varLen="0" name="MailSystem sheet counter

(3

bits)

bit

1"

entity="

page" id="PGOmr3BitsSequenceNumberBit1" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr3BitsSequenceNumberBit2" varLen="0" name="MailSystem sheet counter

(3

bits)

bit

2"

entity="

page" id="PGOmr3BitsSequenceNumberBit2" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsSequenceNumberBit0" varLen="0" name="MailSystem sheet counter

(4

bits)

bit

0"

entity="

page" id="PGOmr4BitsSequenceNumberBit0" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsSequenceNumberBit1" varLen="0" name="MailSystem sheet counter

(4

bits)

bit

1"

entity="

page" id="PGOmr4BitsSequenceNumberBit1" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsSequenceNumberBit2" varLen="0" name="MailSystem sheet counter

(4

bits)

bit

2"

entity="

page" id="PGOmr4BitsSequenceNumberBit2" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr4BitsSequenceNumberBit3" varLen="0" name="MailSystem sheet counter

(4

bits)

bit

3"

entity="

page" id="PGOmr4BitsSequenceNumberBit3" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsSequenceNumberBit0" varLen="0" name="MailSystem sheet counter

(5

bits)

bit

0"

entity="

page" id="PGOmr5BitsSequenceNumberBit0" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsSequenceNumberBit1" varLen="0" name="MailSystem sheet counter

(5

bits)

bit

1"

entity="

page" id="PGOmr5BitsSequenceNumberBit1" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsSequenceNumberBit2" varLen="0" name="MailSystem sheet counter

(5

bits)

bit

2"

entity="

page" id="PGOmr5BitsSequenceNumberBit2" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsSequenceNumberBit3" varLen="0" name="MailSystem sheet counter

(5

bits)

bit

3"

entity="

page" id="PGOmr5BitsSequenceNumberBit3" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="Omr5BitsSequenceNumberBit4" varLen="0" name="MailSystem sheet counter

(5

bits)

bit

4"

entity="

page" id="PGOmr5BitsSequenceNumberBit4" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IsHeader" varLen="0" name="Is the header page" entity="page" id="PGIsHeader" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;omsf:field varName="IsTrailer" varLen="0" name="Is the trailer page" entity="page" id="PGIsTrailer" available="pre" createInstance="none" type="boolean"&gt;

&lt;omsf:description/&gt;

&lt;/omsf:field&gt;

&lt;/omsf:fieldsConfig&gt;

&lt;/buildconfig&gt;

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}