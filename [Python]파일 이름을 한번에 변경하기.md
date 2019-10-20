# [Python]을 이용해 파일 이름을 한번에 변경하기

- 파일 이름에서 특정 단어나 특정 부분을 일괄적으로 변경하고 싶을 때!!
  이 코드를 이용하면 어렵지 않게 변경할 수 있습니다.

  아래 코드는 python 3.7.3 으로 작성했습니다.

  ```python
  import os
  
  files = os.listdir('./')
  
  for file in files:
      if file[-2:] != 'py':
          name = file
          new_name = file.replace('원래 글자', '바꿀 글자')
          name = os.path.join('./', name)
          new_name = os.path.join('./', new_name)
          os.rename(name, new_name)
  ```

  간단합니다. 

  python 파일을 만들고 위 코드를 복붙합니다. 그리고 파일의 원래 글자와 바꾸고 싶은 글자를 안에 넣어 준후 저장하고 python 파일을 파일 이름을 변경할 폴더에 넣고 더블클릭으로 실행해주면 끝!

  ex) '9월'을 모두 '10월'로 변경하고 싶다-> '원래 글자': '9월', '바꿀 글자': '10월'을 넣고 실행시켜주면 됩니다!

  

