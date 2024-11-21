# Homework_10.1



def pow(x):
    return x ** 2

def some_gen(begin, end, func):
    """
    Генераторная функция, которая возвращает элементы последовательности,
    заданной функцией func, начиная с begin и до end (не включительно).
    
    begin: первый элемент последовательности
    end: количество элементов последовательности
    func: функция, которая формирует значения для последовательности
    """
    for i in range(begin, end):
        yield func(i)

from inspect import isgenerator

gen = some_gen(2, 6, pow)
assert isgenerator(gen) == True, 'Test 1'
assert list(gen) == [4, 9, 16, 25], 'Test 2'

print("Все тесты пройдены!")
