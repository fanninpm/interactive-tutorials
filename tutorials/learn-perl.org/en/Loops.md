Tutorial
--------
Like many programming languages Perl offers several loop structures. 
A loop allows to execute statement blocks over and over again, with logical conditions, value lists or control statements being used to control the loop.

The basic loop structures are: 

while COND BLOCK - repeat a statement BLOCK while COND is true. COND is tested before executing BLOCK

	$count = 10;
	while ($count > 0) {
	  print "Countdown is: $count\n";
	  $count--;
	}

until COND BLOCK - repeat a statement BLOCK until COND is true. COND is tested before executing BLOCK

	$count = 1;
	until ($count > 10) {
	  print "Countup is: $count\n";
	  $count++;
	}

for (INIT ; COND ; COMMAND) BLOCK - This is a loop structure similar to C language for loop. Before the loop starts execute INIT as the initialization sequence. Then repeat the statement BLOCK while COND is true. COND is tested before executing BLOCK. After each iteration, execute the COMMAND.

	for ($count = 1 ; $count > 10 ; $count++) {
	  print "My count is: $count\n":
	}

foreach VAR LIST - iterate over all LIST values and each iteration assign VAR to the next value from LIST

	@fibonacci = (1, 1, 2, 3, 5, 8, 13, 21, 34, 55);
	foreach $number (@fibonacci) {
	  print "$number\n"
	}

do BLOCK while COND - repeat a statement BLOCK while COND is true. COND is tested after executing BLOCK

	my $counter = 4;
	my $factorial = 1;
	print "factorial of $counter is ";
	do {
	  $factorial *= $counter--; # Multiply $factorial by $counter, then decrement $counter by 1.
	} while ($counter > 0);
	print "$factorial\n";

### Loop Control Statements

Loop control statements can be placed withing the loop's statement BLOCK. Wnen executed, these will alter the normal loop sequence. Some useful control statements are:

next - causes the loop to skip the rest of the statement block

last - causes the loop to skip the rest of the statement block and exit the loop iterations.

Perl supports loop nesting. This means that statement blocks may include loop structures.

A loop becomes an infinite loop when its condition (COND) is always false. For example, if COND is not specified.


Exercise
-------------
In this exercise, you will need to loop through and print out all even numbers from the numbers list in the same order they are received. Don't print any numbers that come after 237 in the sequence.

Tutorial Code
-------------
	@NUMBERS = (951,402,984,651,360,69,408,319,601,485,980,507,725,547,544,615,83,165,141,501,263,617,865,575,219,390,237,412,566,826,248,866,950,626,949,687,217,815,67,104,58,512,24,892,894,767,553,81,379,843,831,445,742,717,958,609,842,451,688,753,854,685,93,857,440,380,126,721,328,753,470,743,527);

	# write your code below

Expected Output
---------------
	402
	984
	360
	408
	980
	544
	390

Solution
--------

	@NUMBERS = (951,402,984,651,360,69,408,319,601,485,980,507,725,547,544,615,83,165,141,501,263,617,865,575,219,390,237,412,566,826,248,866,950,626,949,687,217,815,67,104,58,512,24,892,894,767,553,81,379,843,831,445,742,717,958,609,842,451,688,753,854,685,93,857,440,380,126,721,328,753,470,743,527);

    foreach (@NUMBERS) {
    	print $_ . "\n" if ($_ % 2 == 0);
        exit if ($_ == 237);
    }
