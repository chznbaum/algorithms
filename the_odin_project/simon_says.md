# Simon Says

## Spec

```
# # Simon Says
#
# ## Topics
#
# * functions
# * strings
# * default parameter values
#
# ## Hints
#
# When you make the second `repeat` test pass, you might break the **first**
#

require "simon_says"

describe "Simon says" do
  describe "echo" do
    it "should echo hello" do
      expect(echo("hello")).to eq("hello")
    end

    it "should echo bye" do
      expect(echo("bye")).to eq("bye")
    end
  end

  describe "shout" do
    it "should shout hello" do
      expect(shout("hello")).to eq("HELLO")
    end

    it "should shout multiple words" do
      expect(shout("hello world")).to eq("HELLO WORLD")
    end
  end

  describe "repeat" do
    it "should repeat" do
      expect(repeat("hello")).to eq("hello hello")
    end

    # Wait a second! How can you make the "repeat" method
    # take one *or* two arguments?
    #
    # Hint: *default values*
    it "should repeat a number of times" do
      expect(repeat("hello", 3)).to eq("hello hello hello")
    end
  end

  describe "start_of_word" do
    it "returns the first letter" do
      expect(start_of_word("hello", 1)).to eq("h")
    end

    it "returns the first two letters" do
      expect(start_of_word("Bob", 2)).to eq("Bo")
    end

    it "returns the first several letters" do
      s = "abcdefg"
      expect(start_of_word(s, 1)).to eq("a")
      expect(start_of_word(s, 2)).to eq("ab")
      expect(start_of_word(s, 3)).to eq("abc")
    end
  end

  describe "first_word" do
    it "tells us the first word of 'Hello World' is 'Hello'" do
      expect(first_word("Hello World")).to eq("Hello")
    end

    it "tells us the first word of 'oh dear' is 'oh'" do
      expect(first_word("oh dear")).to eq("oh")
    end
  end

  describe "titleize" do
    it "capitalizes a word" do
      expect(titleize("jaws")).to eq("Jaws")
    end

    it "capitalizes every word (aka title case)" do
      expect(titleize("david copperfield")).to eq("David Copperfield")
    end

    it "doesn't capitalize 'little words' in a title" do
      expect(titleize("war and peace")).to eq("War and Peace")
    end

    it "does capitalize 'little words' at the start of a title" do
      expect(titleize("the bridge over the river kwai")).to eq("The Bridge over the River Kwai")
    end
  end

end
```

## Solution

```
#write your code here
def echo(expression)
  expression
end
def shout(expression)
  expression.upcase
end
def repeat(expression, number = 2)
  expression_array = []
  (1..number).each { expression_array.push(expression) }
  expression_array.join(" ")
end
def start_of_word(expression, number = 1)
  expression[0, number]
end
def first_word(expression)
  expression_array = expression.split(" ")
  expression_array[0]
end
def titleize(expression)
  expression[0] = expression[0].upcase
  small_words = %w[a aboard about above across after against along amid among an and anti around as at before behind below beneath beside besides between beyond but by concerning considering despite down during except excepting excluding following for from in inside into like minus near nor of off on onto opposite or outside over past per plus regarding round save since than the through to toward towards under underneath unlike until up upon versus via with within without]
  expression_array = expression.split(" ")
  if expression_array.length > 1
  	expression_array.each do |expression|
  	  if small_words.include?(expression)
  	    expression
  	   else 
  	  	expression[0] = expression[0].upcase
  	  end
  	end
  end
  expression = expression_array.join(" ")
end
```