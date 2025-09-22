import math
import numpy

def false_position_a(f,a,b,tol):
    if a >= b or tol <= 0:
        return('This procedure does not apply for a >= b or precision <= 0')
    elif f(a) == 0:
        return a
    elif f(b) == 0:
        return b
    elif numpy.sign(f(a)) == numpy.sign(f(b)):
        return ('The function has no root in this range')
    else:
        while (b-a) > tol:
            #print(a)         
            #print(b)
            p = (a*f(b) - b*f(a))/(f(b) - f(a))
            if f(p) == 0:
                return(p)
            elif numpy.sign(f(a)) == numpy.sign(f(p)):
                a = p
            else:
                b = p
        return((a*f(b) - b*f(a))/(f(b) - f(a)))
