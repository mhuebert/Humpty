Baa, baa,

    def english_to_sheep(message):
        message_words = message.split()
        print ["baa" for word in message_words]

    english_to_sheep("Hi there")

black sheep,

    class Sheep(object):
        def __init__(self, color, lbs_wool):
            self.color = color
            self.lbs_wool = lbs_wool

        def has_wool(self):
            if self.lbs_wool in [None, 0]:
                return False
            else:
                return True

    black_sheep = Sheep(color="black", lbs_wool=36)

Have you any wool?

    black_sheep.has_wool()

Yes, sir, yes, sir,
Three bags full;

    bag_capacity = 10
    how_many_bags = black_sheep.lbs_wool//bag_capacity

One for the master,

    class Person(object):
        def __init__(self):
            self.bags_wool = 0

    def give_bag_of_wool(sheep, recipient):
        sheep.lbs_wool -= bag_capacity
        recipient.bags_wool += 1

    master = Person()
    give_bag_of_wool(black_sheep, master)

And one for the dame,

    dame = Person()
    give_bag_of_wool(black_sheep, dame)

And one for the little boy
Who lives down the lane.

    little_boy_who_lives_down_the_lane = Person()
    give_bag_of_wool(black_sheep, little_boy_who_lives_down_the_lane)

Baa, baa, black sheep

    english_to_sheep("Hi again")

Have you any wool?

    black_sheep.has_wool()

...Yes, but not very much!

    black_sheep.lbs_wool