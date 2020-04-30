# Отчёт о тестировании <IntelliJ IDEA>
## Краткое описание
<30.04.20> - <30.04.20> было проведено приложение **IntelliJ IDEA**

На тестирование затрачено:*<1 час>*

### Описание процесса тестирования

**В процессе тестирования использовались следующие артефакты:**

•  Руководство по установке IntelliJ IDEA  
•  freeformatter.com
### В качестве тестовых данных использовались:

    public class Main {
    
    public static void main(String[] args) {
        
        String number = "4716666765065474";
        
        System.out.println(String.format("Result is %s", 
        
        isValidCardNumber(number) ? "OK" : "FAIL"));
    }

    public static boolean isValidCardNumber(String number) {
        if (number == null) {
            return false;
        }

        if (number.length() != 16) {
            return false;
        }

        long result = 0;
        for (int i = 0; i < number.length(); i++) {
            int digit;
            try {
                digit = Integer.parseInt(number.charAt(i) + "");
            } catch (NumberFormatException e) {
                return false;
            }

            if (i % 2 == 0) {
                digit *= 2;
                if (digit > 9) {
                    digit -= 9;
                }
            }
            result += digit;
        }

        return (result != 0) && (result % 10 == 0);
    }
    
    }

### Результат:

***Result is OK***

***Process finished with exit code 0***

### Тестирование производилось в следующем окружении:

•  Windows 10Pro x86

•  Java 11

•  IntelliJ IDEA

