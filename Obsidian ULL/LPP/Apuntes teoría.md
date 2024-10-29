```ruby
class Point
	#métodos de acceso
	attr_reader :x, :y #getters
	attr_writter :x, :y #setters
	attr_acessor :x, :y	
	
	def initialize(x,y)
	    @x, @y = x, y
	    if defined?(@@number_of_points)
			@@number_of_points += 1
	    else
		    @@number_of_points = 1
	    end
	end
	
	def +(other)
		Point.new(@x + other.x, @y + other.y)
	end
	def *(value)
		Point.new(@x * value, @y * value)
	end
end
```
