### [python] 을 이용한 xlsx 데이터 모으기

#### python 3.9 사용

#### openpyxl 설치
    pip install openpyxl
<br>

#### xlsx 파일이름 필터링(정규표현식 고려중)
    files = os.listdir()
    xlsx_files = list(filter(lambda name: True if name.find('.xlsx') >= 0 else False, files))
<br>

#### col 지정(데이터 열이 많아질 경우 index를 이용할 예정)
    cols = ['A', 'B']
<br>

#### 작성되는 파일 이름
    file_name = "union.xlsx"
<br>

#### 모든 열에 데이터가 있는 지 체크
    any(list(map(lambda col: sheet[col + str(idx)].value is not None, cols)))
