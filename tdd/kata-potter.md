# Kata Potter

**Problem Description**

Once upon a time there was a series of 5 books about a very English hero
called Harry. Children all over the world thought he was fantastic, and, of
course, so did the publisher. So in a gesture of immense generosity to
mankind, (and to increase sales) they set up the following pricing model to
take advantage of Harry's magical powers.

One copy of any of the five books costs 8 EUR. If, however, you buy two
different books from the series, you get a 5% discount on those two books.
If you buy 3 different books, you get a 10% discount. With 4 different books,
you get a 20% discount. If you go the whole hog, and buy all 5, you get a
huge 25% discount.

Note that if you buy, say, four books, of which 3 are different titles, you
get a 10% discount on the 3 that form part of a set, but the fourth book
still costs 8 EUR.

Your mission is to write a piece of code to calculate the price of any
conceivable shopping basket, giving as big a discount as possible.

For example, how much does this basket of books cost?

    2 copies of the first book
    2 copies of the second book
    2 copies of the third book
    1 copy of the fourth book
    1 copy of the fifth book

(answer: 51.20 EUR)

**Clues**

You’ll find that this Kata is easy at the start. You can get going with
tests for baskets of 0 books, 1 book, 2 identical books, 2 different
books... and it is not too difficult to work in small steps and gradually
introduce complexity.

However, the twist becomes apparent when you sit down and work out how
much you think the sample basket above should cost.

It isn’t 

      5 * 8 * 0.75
    + 3 * 8 * 0.90

It is in fact

      4 * 8 * 0.8
    + 4 * 8 * 0.8

So the trick with this Kata is not that the acceptance test you’ve been
given is wrong. The trick is that you have to write some code that is
intelligent enough to notice that two sets of four books is cheaper than
a set of five and a set of three.

You will have to introduce a certain amount of clever optimization
algorithm. But not too much! This problem does not require a fully
fledged general purpose optimizer. Try to solve just this problem well
in order to share it for everyone. Trust that you can generalize and
improve your solution if and when new requirements come along.

**Suggested Test Cases**

    def testBasics
      assert_equal(0, price([]))
      assert_equal(8, price([0]))
      assert_equal(8, price([1]))
      assert_equal(8, price([2]))
      assert_equal(8, price([3]))
      assert_equal(8, price([4]))
      assert_equal(8 * 2, price([0, 0]))
      assert_equal(8 * 3, price([1, 1, 1]))
    end
    
    def testSimpleDiscounts
      assert_equal(8 * 2 * 0.95, price([0, 1]))
      assert_equal(8 * 3 * 0.9, price([0, 2, 4]))
      assert_equal(8 * 4 * 0.8, price([0, 1, 2, 4]))
      assert_equal(8 * 5 * 0.75, price([0, 1, 2, 3, 4]))
    end
    
    def testSeveralDiscounts
      assert_equal(8 + (8 * 2 * 0.95), price([0, 0, 1]))
      assert_equal(2 * (8 * 2 * 0.95), price([0, 0, 1, 1]))
      assert_equal((8 * 4 * 0.8) + (8 * 2 * 0.95), price([0, 0, 1, 2, 2, 3]))
      assert_equal(8 + (8 * 5 * 0.75), price([0, 1, 1, 2, 3, 4]))
    end

    def testEdgeCases
      assert_equal(2 * (8 * 4 * 0.8), price([0, 0, 1, 1, 2, 2, 3, 4]))
      assert_equal(3 * (8 * 5 * 0.75) + 2 * (8 * 4 * 0.8), 
        price([0, 0, 0, 0, 0, 
               1, 1, 1, 1, 1, 
               2, 2, 2, 2, 
               3, 3, 3, 3, 3, 
               4, 4, 4, 4]))
    end

Reference: [Kata Potter][1]

## Presentation

Once upon a time there was a series of 5 books about a very English hero
called Harry. Children all over the world thought he was fantastic, and, of
course, so did the publisher. So in a gesture of immense generosity to
mankind, (and to increase sales) they set up the following pricing model to
take advantage of Harry's magical powers.

Your mission is to write a piece of code to calculate the price of any
conceivable shopping basket containig only Harry's books

## Steps

1.  Create a function which receives a shopping basket and returns its total
    price having that each book costs 8 EUR.
2.  If you buy 2 different books, you get a 5% discount on those 2 books. 
4.  If you buy 3 different books, you get a 10% discount.
5.  If you buy, say, four books, of which 3 are different titles, you get a
    10% discount on the 3 that form part of a set, but the fourth book still
    costs 8 EUR.
5.  With 4 different books, you get a 20% discount.
6.  If you go the whole hog, and buy all 5, you get a huge 25% discount.
7.  You must calculate the price of any conceivable shopping basket.
8.  You must give the biggest discount as possible.


[1]: http://codingdojo.org/cgi-bin/index.pl?KataPotter
