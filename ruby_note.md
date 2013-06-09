Ruby
=======
**reading note**

###Ruby is an Object-Oriented Language

* *Everything you manipulate is an object, and the resuils of those manipulations are themselves objects.*

* *Instance*(实例变量)

	Once you have these classes, you'll typically want to create a number of *Instances* of each.

	for example a class named Song:
	
		song1 = Song.new("Ruby Tuesday")
		song2 = Song.new("Enveloped in Python")
	
	"Ruby Tuesday" and "Enveloped in Python" are *Instances*
	
	These instances are both derived(源自) frome the same class, but they have unique characteristics.  First, every object has a unique object identifier(abbreviated(缩写) as object id). Second, you can define instance variables, variables with values that are unique to each instance. These instance variables hold an object's state. Each of our songs, for example, will probably have an instance variable that holds the song title.
	
###Some Basic Ruby

#### parentheses

	def sayGoodnight(name)
		result = "Goodnight, " + name
		return result
	end
	
	#Time for bed
	puts sayGoodnight("John-Boy")
	puts sayGoodnight("Mary-Ellen")	
	
matter of parentheses(圆括号), following are equivalent

-->

	puts sayGoodnight "John-Boy"
	puts sayGoodnight ("John-Boy")
	puts(sayGoodnight "John-Boy")
	puts(sayGoodnight("John-Boy"))
	
####In the double-quoted case

Firstly, it looks for substitutions(替换). "\n".


Secondly, expression interpolation. #{expression}

	def sayGoodnight (name)
		"Goodnight, #{name}"
	end
	
####names

* local variables, method parameters, and method names should all start with a lower case lerrer
*  Global variables with $
*  instance variables with @
*  class variables with @@
*  class names, module names, and constants should start with an uppercase letter.


###Arrays and Hashes
####Arrays

	a = [ 1, 'cat', 3.14 ] 
	a[0]		>> 1
	a[2] = nil
	a			>> [1, 'cat', nil]	 

using **Array.new**

	empty = []
	empty = Array.new
	
creating array with words

	a = %w{ ant bee cat dog elk }
	a[0]		>>		"ant"
	a[3]		>>		"dog"

####Hashes

	instSection = {
		'cello'		=>	'string',
		'clarinet'	=>	'woodwind'
	}
	
indexed same as arrays

	instSection[ 'oboe' ]		>> "woodwind"
	
using **Hash.new**

	histogram = Hash.new(0)
	histogram['key1']		>>	0
	histogram['key1'] = histogram ['key1'] +1
	histogram['key1']		>>	1
	
###Control Structures
	if count > 10
		puts "Try again"
	elsif treis == 3
		puts "You lose"
	else
		puts "Enter a number"
	end
	

	while weight < 100 and numPallets <= 30
		pallet = nextPallet()
		weight += pallet.weight
		numPallets +=1
	end
	
####shortcut for *if* and *while*
######if

	if radiation > 3000
		puts "Danger, Will Robinson"
	end
	
-->

	puts "Danger, Will Robinson" if radiation > 3000
	
#####while

	while square < 1000
		square = square*square
	end
	
-->

	square = square*square while square < 1000
	
###Regular Expression

	/Perl|Python/

-->
	
	/P(erl|ython)

other examples

	/ab+c/	#matches a string containing an a followed by one or more b's, followed by a c.
	/ab*c/	#matches a string containing one a, followed by zero or more b's, followed by a c.

	/\d\d:\d\d:\d\d/			# a time such as 12:34:56
	/Perl.*Python/				# Perl, zero or more other chats, then Python
	/Perl Python/				# Perl, a space, and Python
	/Perl *Python/				# Perl, zero or more space, and Python
	/Perl +Python/				# Perl, one or more space, and Python
	/Perl\s+Python/				# Perl, whitespace characters, then Python
	/Ruby (Perl|Python)/		# Perl, a space, and either Perl or Python

	if line =~ /Perl|Python/
		puts "Scripting language mentioned: #{line}" 
	end
	
	line.sub(/Perl/, 'Ruby') 	# replace first 'Perl' with 'Ruby'
	line.gsub(/Python/, 'Ruby') 	# replace every 'Python' with 'Ruby'

	line.gsub(/Perl|Python/, 'Ruby') 

###Blocks and Iterators

	animals = %w( ant bee cat dog elk)
	animals.each { |animal| puts animal }

	#produces:

	ant
	bee
	cat
	dog
	elk


	[ 'cat', 'dog', 'horse' ].each {|name| print name. " " }
	5.times { print "*"}
	3.upto(6) {|i| print i }
	('a'..'e').each {|char| print char }

	#produces:

	cat dog horse *****3456abcde

###Reading and 'Riting

	printf("Nummer: %5.2f,\nString: %s\n", 1.23, "hello")

	#produces:

	Nummer: 1.23
	String: hello

	line = gets
	print line

~~~~~~~~~~~~
\begin{Math}
f(x) = \frac{a}{1-a^2}
\end{Math}
~~~~~~~~~~~~
