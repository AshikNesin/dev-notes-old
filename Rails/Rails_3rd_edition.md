<% provide(:title,"About") %>


<%= yield(:title) %>


### Ruby BASICs for Rails

first_name = "Ashik"

**String Interpolation**

puts "#{first_name} Nesin"


puts -> New Line at the end

print -> No new line at the end

'' (**single quotes**) doesn't allow interpolation

```
 puts '#{first_name} Nesin' => #{first_name} Nesin

```


### Methods

Everything in Ruby is Object

object_name.method

.length

.empty?	(Boolean Method)

.include?("some_text")

.to_s

.nil? (nil is ONLY thing)

if condition

elsif

end


(statement) if conditon && !condition

It'll return nil no matter whether it is TRUE or FALSE. If the stmt is true it'll execute block

**method chaining**

nil.to_s.empty?

puts 'something' unless x.empty?


**Note**

Everything except false, nil is FALSE

Not even 0.

### Function

def string_msg(str='')
  if condition
  
  else

  end
end

puts string_msg('Hello')

### split method

str = "foo bar baz"

str.split

=>["foo","bar","baz"]

str.split(",") 

### arrays

Ruby array can have different data types
arr=["foo","bar","baz"]

a= %w[foo bar baz]

arr[-1] => bar

.empty?

.include?()

.sort

.reverse

.shuffle

These methods will actually doesnt change the array. If we need to change those methods then we'll need to **BANG(!)** it.

.push()

arr << "foo" << "bar"

.join

.join(", ")


### Ranges

0..9

arr = (0..9).to_a

arr[4..(a.length-1)] OR arr [4..-1]

### Block

Single Line

arr.each { | x | puts x}    **{stmt1;stmt2;..}**


arr.each do | x |
	puts x
end


.times


3.times {puts "Hey"}

Calculate Square

square = []

(1..25).each { |x| square << x**2}


square = (1..5).map {|x| x**2}

%w[A B C].map{ |char|.downcase }

%w[A B C].map{ |char|.uppercase }

%w[A B C].map(&:downcase)


