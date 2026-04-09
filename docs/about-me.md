# Introduce
**CS** sophomore TaeHyeon Lee

## Skill Stack
 - Python - C
 - Java
 - Git & GitHub

## Code Sample

```C
switch (Choice_Index) {
case 1:
	printf("Decimal number: ");
	if (scanf("%lld", &Decimal_Input) != 1) {
		printf("오류: 정수를 입력하세요!\n");
		goto HANDLE_ERROR_DEFAULT;
	}
	break;

case 2:
	printf("Enter the number system(max: 16): ");
	if (scanf("%hd", &Base_Input) != 1 || Base_Input < 2 || Base_Input > 16) {
		printf("오류: 16 이하, 2 이상의 양수를 입력하세요!\n");
		goto HANDLE_ERROR_DEFAULT;
	}

	long long Deep_Decimal_Input = Decimal_Input; // 원본 소실 방지를 위한 값 복사
	
	if (Deep_Decimal_Input < 0) {
			printf("-"); // 출력문은 char 형태로, 개행과 공백 없이 printf() 함수로 연결
			Deep_Decimal_Input = Deep_Decimal_Input * -1; // 음수의 경우, 양수 앞에 "-" 출력 형태
		}

	do {
		Push(s, Deep_Decimal_Input % Base_Input); // 나머지를 역순으로 추출할 예정
		
		Deep_Decimal_Input = Deep_Decimal_Input / Base_Input;

	} while (Deep_Decimal_Input > 0); // Decimal_Input이 0인 경우에 대한 do-while 예외 처리

	while (!Is_Empty(s)) {
		long long data = Pop(s);
		if (data < 10) {
			printf("%c", data + '0');
		}
		else {
			printf("%c", data - 10 + 'A');
		}
	}
	printf("\n");
	break;

case 3:
	goto CLEANUP_AND_EXIT;

HANDLE_ERROR_DEFAULT:
default:
	while (getchar() != '\n');
	printf(MENU_TEXT);
	break;
}
```

## Class List

| - | - |
|------|-------|
| Freshman | A Class |
| Sophomore | B Class |
