!SLIDE bullets incremental
# Testy jednostkowe #
## Narzędzia ##
* JUnit
* jqunit, Jasmine
* NUnit
* PHPUnit, lime
* Test::More, Test::Unit - PerlUnit
* Test::Unit, RSpec, MiniTest

!SLIDE small
# Przykład - JUnit #

    @@@Java
    public class CalculatorTest extends TestCase {
      private Calculator calculator;
      
      @Before public void setUp() {
        calculator = new Calculator();
      }
      
      @Test public void testDivideTwoNumbers() {
        result = calculator.div(6,3);
        assertEquals(2, result);
      }
      
      @Test(expected=java.lang.ArithmeticException.class)
      public void testDivideByZero() {
        calculator.div(6,0)
      }
    }

!SLIDE small
# Przykład - PHPUnit #

    @@@PHP
    class CalculatorTest extends PHPUnit_Framework_TestCase {
      
      protected function setUp() {
        $this->calculator = new Calculator;
      }
      
      public function testDivideTwoNumbers {
      }
      
      /**
      * @expectedException InvalidArgumentException
      */
      public function testDivideByZero() {
      }
    }

!SLIDE small
# Przykład - Test::Unit #

    @@@Ruby
    class CalculatorTest < Test::Unit::TestCase
    
      def setup
        @calculator = Calculator.new
      end
      
      test "when divide two numbers when divide two numbers" do
        result = @calculator.div(6,3)
        assert_equal 2, result
      end
      
      test "when divide number by 0 it raise exception" do
        assert_raised(ZeroDivisionError) { @calculator.div(6,0) }
      end
    end

!SLIDE smaller
# Przykład - RSpec #

    @@@Ruby
    describe Calculator do
      subject { Calculator.new }
      
      describe "division" do
        it "should return number when divide two numbers" do
          subject.div(6,2).should equal 2
        end
        
        it "should raise an exception when divide by zero" do
          lambda { subject.div(6,0) }.should raise_error(ZeroDivisionError)
        end
      end
    end

!SLIDE
# Mock #

!SLIDE smaller

    @@@Ruby
    def test_create_success
      new_contact_attrs = {"name" => "John Doe",
        "email" => "john.d@somewhere.com", "campaign" => "campaignId",
        "customs" => {"source" => "mainpage"}}
      attrs_sent_to_service = new_contact_attrs.merge("customs" => [
        {"name" => "source", "content" => "mainpage"}])
  
      mock(@connection).send_request(:add_contact,attrs_sent_to_service) do
        {'result' => {'queued' => 1}}
      end
      contact = @proxy.create(new_contact_attrs)
  
      assert_kind_of GetResponse::Contact, contact
    end