## **Herencia** 

```ruby
require 'pry'

class Point
	#métodos de acceso
	attr_reader :x, :y #getters 
	attr_writter :x, :y #setters
	attr_acessor :x, :y	
	
	def initialize(x,y) #constructor de la clase
	    @x, @y = x, y
	    if defined?(@@number_of_points)
		# @@ significa variable global entre las clases lo que permite que se
		#ejecute desde cualquiera de estas.
			@@number_of_points += 1
	    else
		    @@number_of_points = 1
	    end
	end
	
	#método para devolver el contrario
	def -@
		Point.new(-@x, -@y)
	end
	
	#método de suma
	def +(other) 
		Point.new(@x + other.x, @y + other.y)
	end
	
	#método de multiplicación
	def *(value) 
		Point.new(@x * value, @y * value)
	end
	
	#método para saber el número de points creado
	def self.count
		@@number_of_points
	end
	
	def to_s #invalidando 
	    "( #{@x}, #{@y} )"
	end
	
	#constante
	ORIGIN = Point.new(0, 0) 
end
```
Point.superclass //Consigo la clase padre del objeto

``` ruby
require 'point'

# Herencia
# Cuando una clase está basada en otra,
# y crea una nueva implementación 
# que mantiene el mismos comportamiento y 
# añade nuevas funcionalidades 
class Point3D < Point
	attr_reader :z
	def initialize (x, y, z)
		#LLamo al initialize de arriba, encadenamiento
		super(x, y) 
		@z = z
	end
	
	#invalidando (overriding)
	#  def to_s
	#    "(#{@x}, #{@y}, #{@z})"
	#  end
	def to_s
	    s = "( "
	    s << super.to_s        #encadenamiento (chaining)
	    s << ", #{@z} )"
	    s
	end
	
	ORIGIN = Point3D.new(0, 0, 0)
end
```