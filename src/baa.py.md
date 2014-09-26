Baa, baa,

    >>> def english_to_sheep(message):
    ...     message_words = message.split()
    ...     print " ".join(["baa" for word in message_words])

    >>> english_to_sheep("Hi there")
    baa baa

black sheep,

    >>> class Sheep(object):
    ...     def __init__(self, color, lbs_wool):
    ...     self.color = color
    ...     self.lbs_wool = lbs_wool

    >>> def has_wool(self):
    ...     if self.lbs_wool in [None, 0]:
    ...         return False
    ...     else:
    ...         return True

    >>> black_sheep = Sheep(color="black", lbs_wool=32)

Have you any wool?

    >>> black_sheep.has_wool()
    True

Yes, sir, yes, sir, three bags full;

    >>> bag_capacity = 10
    >>> how_many_bags = black_sheep.lbs_wool//bag_capacity
    >>> how_many_bags
    3

One for the master,

    >>> class Person(object):
    ...     def __init__(self, name):
    ...         self.name = name
    ...         self.bags_wool = 0
    ...     def __str__(self):
    ...         return "Name: %s; bags of wool: %s" % (self.name, self.bags_wool)

    >>> def give_bag_of_wool(sheep, recipient):
    ...     sheep.lbs_wool -= bag_capacity
    ...     recipient.bags_wool += 1

    >>> master = Person("Master")
    >>> print Master
    Name: Master; bags of wool: 0
    >>> give_bag_of_wool(black_sheep, master)
    >>> print master
    Name: Master; bags of wool: 1

And one for the dame,

    >>> dame = Person("Dame")
    >>> print dame
    Name: Dame; bags of wool: 0
    >>> give_bag_of_wool(black_sheep, dame)
    >>> print dame
    Name: Dame; bags of wool: 1

And one for the little boy who lives down the lane.

    >>> little_boy_who_lives_down_the_lane = Person("Fred")
    >>> print little_boy_who_lives_down_the_lane
    Name: Fred; bags of wool: 0
    >>> give_bag_of_wool(black_sheep, little_boy_who_lives_down_the_lane)
    >>> print little_boy_who_lives_down_the_lane
    Name: Fred; bags of wool: 1

Baa, baa, black sheep

    >>> english_to_sheep("Hi again")
    baa baa

Have you any wool?

    >>> black_sheep.has_wool()
    True

...Yes, but not very much!

    >>> black_sheep.lbs_wool
    2