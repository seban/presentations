!SLIDE bullets incremental
# Testy akceptacyjne #
## Narzędzia ##
* Fitenesse (java)
* watir
* Selenium
* Concordion (java)
* Cucumber (ruby)

!SLIDE small
## Przykład - Selenium ##
    
    @@@Java
    public class DivisionTest {
      @Test(description = "Division")
      public void divisionRegular() {
        driver.get("http://my.calculator.com")
        driver.findElement(By.id("number-3")).click();
        driver.findElement(By.id("number-2")).click();
        driver.findElement(By.id("division")).click();
        Assert.assertEquals(
          driver.findElement(By.id("division")).getText(),
          "1.5"
        )
      }
    }

!SLIDE center
## Selenium IDE ##
![Selenium IDE](selenium-ide.gif)

!SLIDE center
![Cucumber logo](cucumber-logo.png)

!SLIDE
    @@@Cucumber
    Feature: Division
      In order to avoid silly mistakes
      Cashiers must be able to calculate a fraction
    Scenario: Regular numbers
      * I have entered 3 into the calculator
      * I have entered 2 into the calculator
      * I press divide
      * the result should be 1.5 on the screen
      
!SLIDE center
![Awesome](Awesome.jpg)

!SLIDE
    @@@Cucumber
    Właściwość: Dzielenie
      W celu uniknięcia głupich błędów
      Kasjer musi znać się na ułamkach
    Scenariusz: Zwykłe liczby
      Zakładając wprowadzenie do kalkulatora liczby 3
      Oraz wprowadzenie do kalkulatora liczby 2
      Jeżeli nacisnę podziel
      Wtedy rezultat 1.5 wyświetli się na ekranie
