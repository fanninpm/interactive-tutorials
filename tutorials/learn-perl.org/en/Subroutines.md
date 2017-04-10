Tutorial
--------
A subroutine (or sometimes refered to as function or method) is a group of statements that work together to perform a task. Usually a repeated task which can be invoked several times. 

The general form of a subroutine definition in perl is:

    sub subroutine_name {
    	body of subroutine
    }

Subroutine definitions can be placed anywhere in the program code. It is typical to place these definitions at the beginning of the code before the main code body which calls (uses) these subroutines.

The typical way of calling that Perl subroutine is as follows:

    subroutine_name( list of arguments );

Example 

	# Subroutine definition
	sub Hello{
	   print "Hello, World!\n";
	}

	# Subroutine call
        print "We are calling the subroutine hello() now\n";
	Hello();

Passing Arguments to a Subroutine:

Arguments can be passed to the subroutine by writing them as a comma-delimited list inside the ().
Inside the subroutine, these arguments are accessible using the special array @_. The first argument to the function is in $_[0], the second is in $_[1], and so on.

     # subroutine definition
     sub calc_average {
        # get total number of arguments passed.
        $total_args = scalar(@_);
        $sum = 0;
	# sum up all arguments
        foreach $arg (@_){
           $sum += $arg;
        }
        # calc and print average
        $average = $sum / $total_args;
        print "Average of list [ @_ ] is: $average\n";
     }    

     # subroutine call
     print "We are calling the subroutine calc_average() now\n";
     calc_average(10, 20, 30);
     print "We are calling the subroutine calc_average() again\n";
     calc_average(10, 15, 2, 8, 90);

Passing arrays or hashes to Subroutines

When one wishes to pass an array or hash to a subroutine, it is useful to create a reference and pass it as a single scalar to the subroutine. Then dereferencing the reference inside the subroutine will result with the original array or hash.

     # subroutine definition
     sub is_value_exists_in_array {
       # first argument: string value to be searched in array
       $value = $_[0];
       # second argument: reference to array to be searched in
       $arrayref = $_[1];
       # create the array by dereferencing
       @my_array = @$arrayref;
       my $result = "does not exist in";
       foreach my $element (@array) {
         if ($element eq $value) {$result = "exists in"; last};
       }
       # print result
       print "Value $value $result array @my_array\n";
     }

     # subroutine call
     @foo = ('we', 'are', 5, 'happy', 'perl', 'programmers');
     print "We are calling the subroutine is_value_exists_in_array() now\n";
     is_value_exists_in_array('hello',$foo_arrayref);
     print "We are calling the subroutine is_value_exists_in_array() again\n";
     is_value_exists_in_array('happy',$foo_arrayref);

Returning Value from a Subroutine:

A value can be returned from a subroutine by using the return() function. When this function is used, the subroutine executed is completed. The retun value is a single value. Therefore in order to return an array or hash, create a reference first and return that value.

     # subroutine definition
     sub calc_average {
        # get total number of arguments passed.
        $total_args = scalar(@_);
        $sum = 0;
	# sum up all arguments
        foreach $arg (@_){
           $sum += $arg;
        }
        # calc and print average
        $average = $sum / $total_args;
        return ($average);
     }    

     # subroutine call
     $a = calc_average(10, 20, 30);
     print "The average is $a\n";
     $a = calc_average(10, 15, 2, 8, 90);
     print "The average is $a\n";

Exercise
-------------
Create two subroutines min() and max() which calculate minimum and maximum numeric value of their arguments.
For each given array @car_prices and @flight_prices in the tutorial code, calculate and print the difference between the maximum and minimum values.

Tutorial Code
-------------
    @car_prices = (100, 250, 95, 1300, 4534, 102, 100, 97);
    @flight_prices = (85.20, 79.99, 45.30, 130, 45.34, 110.25, 100, 917);
    # define subroutines
    sub min {
    }
    sub max {
    }
    # write code below

Expected Output
---------------
    4439
    871.7

Solution
--------
