# [Python]을 이용해 파일 이름을 한번에 변경하기

- 파일 이름에서 특정 단어나 특정 부분을 일괄적으로 변경하고 싶을 때!!
  이 코드를 이용하면 어렵지 않게 변경할 수 있습니다.

  아래 코드는 python 3.7.3 으로 작성했습니다.

  - 쉬운설명버젼

  ```python
  # os 모듈을 호출한다.
  import os
  
  # 괄호안에 현재 작성중인 파이썬 파일이 저장되어 있는 위치를 기준으로 바꿀 파일들이 들어가있느 폴더 위치를 설정해 줍니다. '..': 상위폴더라는 뜻
  files = os.listdir('../../../music')
  
  
  for name in files:
      #                이 부분에 다시 폴더위치를 써줍니다.
      name = os.path.join('../../../music', name)
      #										이 부분에 바꿀 파일 이름을 써줍니다.
      new_name = os.path.join('../../../music', name[6:])
      # 지금같은 경우는 파일명의 앞 6글자를 잘라낸다는 뜻입니다. 
      
      
      
  
      # os.rename 메소드를 이용해 파일이름을 변경해준다.
      os.rename(name, new_name)
  
      ## 끝 ## 
  ```

  

  ```python
  ## 파일명 일괄 변경하기 ##
  
  
  # os 모듈을 호출한다.
  import os
  
  # os.listdir 메소드를 이용해 files에 파일이름의 리스트를 저장한다.
  # 이 때, 파라미터로 폴더명이 들어가는데 폴더명은 python 파일 기준의 상대위치로 지정해 준다.
  files = os.listdir('../../../music')
  
  # files에 파일 이름들을 저장해 뒀으니 새 이름을 부여하기위해 for문으로 파일 이름을 순회한다.
  for name in files:
      # 변경할 파일이름을 다시 지정해 준다. files에는 파일이름만 리스트로 저장되어 있다. 하지만 파일명을 바꾸기 위해 os.rename 메소드를 사용하려면 경로까지 이름에 포함되어 있어야 한다.
      # 그러므로 os.path.join 메소드를 이용해 파일 이름에 경로를 추가해 준다.
      # 이렇게 하게 되면 name변수에는 '../../../music/파일이름' 이 저장된다. 
      name = os.path.join('../../../music', name)
  
      # 새 이름을 지정해 준다. 이름을 지정할 때는 마찬가지로 경로가 필요하므로 os.path.join 메소드를 이용해 파일 이름을 경로 + 원하는 파일이름으로 만들어 준다.
      # 아래의 경우에는 name[6:]과 같이 슬라이싱을 이용해 이름 앞의 6자리를 잘라내었다.
      new_name = os.path.join('../../../music', name[6:])
  
      # os.rename 메소드를 이용해 파일이름을 변경해준다.
      os.rename(name, new_name)
  
      ## 끝 ## 
  ```

  

