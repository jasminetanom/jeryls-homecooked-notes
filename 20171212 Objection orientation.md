# Classes
object is a class, put object if you dont want inheritance
class Human(object):


   # A class attribute. It is shared by all instances of this class
   species = "H. sapiens"

   # Basic initializer, this is called when this class is instantiated.
   def __init__(self, name):
  	 	# Assign the argument to the instance's name attribute
  		self.name = name

   # An instance method. All methods take "self" as the first argument
   def say(self, msg):
	   return "%s: %s" % (self.name, msg)

   # A class method is shared among all instances
   # They are called with the calling class as the first argument
   @classmethod 
  def get_species(cls):
        return cls.species