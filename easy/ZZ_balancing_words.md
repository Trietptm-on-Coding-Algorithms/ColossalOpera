# Title

[2015-07-06] Challenge #222 [Easy] Balancing Words

# Difficulty

Easy

# Tags

letter sums, word games

# Description

Today we're going to balance words on one of the letters in them. We'll use the position and letter itself to calculate the weight around the balance point. A word can be balanced if the weight on either side of the balance point is equal. Not all words can be balanced, but those that can are interesting for this challenge.

The formula to calculate the weight of the word is to look at the letter position in the English alphabet (so A=1, B=2, C=3 ... Z=26) as the letter weight, then multiply that by the distance from the balance point, so the first letter away is multiplied by 1, the second away by 2, etc. 

As an example:

STEAD balances at T: 1 * S(19) = 1 * E(5) + 2 * A(1) + 3 * D(4))

More info [here](http://www.questrel.com/records.html#spelling_alphabetical_order_entire_word_balance_points) on the Questrel site.

# Input Description

You'll be given a series of English words. Example:

    STEAD

# Output Description

Your program or function should emit the words split by their balance point and the weight on either side of the balance point. Example:

    S T EAD - 19
    
This indicates that the T is the balance point and that the weight on either side is 19.

# Challenge Input

    CONSUBSTANTIATION
    WRONGHEADED
    UNINTELLIGIBILITY

# Challenge Output

	CONSUBST A NTIATION - 456
	WRO N GHEADED - 120
	UNINTELL I GIBILITY - 521
    
# Notes

This was found on a word games page suggested by /u/cDull, thanks! If you have your own idea for a challenge, submit it to /r/DailyProgrammer_Ideas, and there's a good chance we'll post it.

# Scala Solution

	def balance(word:String): (String, String, String, Int) = {
	  def loop(word:String, n:Int):(Int, Int) = {
	    n+word.length match {
	      case 1 =>       (0, -1)
	      case _ =>
	        val p = word.map(_.toInt-64).zip(n to (word.length+n-1)).map(x=>x._1*x._2).partition(_>0)
	        val lhs = p._1.sum
	        val rhs = p._2.sum
	        (lhs + rhs == 0) match {
	          case true  => (lhs, (n to (word.length+n-1)).indexOf(0))
	          case false => loop(word, n-1)
	        }
	    }
	  }
	  val b = loop(word.toUpperCase, 0)
	  b._1 match {
	    case 0 => ("", "", "", -1)
	    case _ => (word.substring(0, b._2), word(b._2).toString, word.substring(b._2+1, word.length), b._1)
	  }
	}

	// how many words can be balanced?
	val bwords = scala.io.Source.
	              fromFile("/usr/share/dict/words").
	              getLines.
	              map(balance(_)).
	              filter(_._1 != "")
