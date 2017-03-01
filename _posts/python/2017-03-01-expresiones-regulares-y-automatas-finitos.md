---
layout: default
comments: true
intro: Recursos para saber más de expresiones regulares
title: Expresiones Regulares y Autómatas finitos
category: python
meta_contenido: Expresiones Regulares y Autómatas finitos
date: 2017-03-01T14:51:00Z
---

<h1 class="centrar-titulo-blog">{{page.title}}</h1>

El tema de las expresiones regulares y su aplicación y fundamentación teórica son tratados en los cursos de Udacity
y Stanford Lagunita respectivamente:

* Udacity: Lenguajes de programación ([Programming Languages](https://www.udacity.com/course/programming-languages--cs262){:target="_blank"}).
* Stanford Lagunita: Teoría de autómatas ([Automata Theory](https://lagunita.stanford.edu/courses/course-v1:ComputerScience+Automata+SelfPaced/about){:target="_blank"}).

En el curso de Udacity se usa python para analizar el código html y javascript como cadenas
de texto y de modo que lo interprete tal como lo haría un navegador Web. 

<div class="foto-center">
  <img class="img-adaptable" src="{{site.baseurl}}/imagenes/automaton2.jpg" alt="automaton" />
  <figcaption>Representación de una expresión regular</figcaption>
</div>
Este es el código Python que simula el anterior autómata finito tomado de un quiz del curso de Udacity:
{% highlight python %}
edges = {(1, 'a') : 2,
         (2, 'a') : 2,
         (2, '1') : 3,
         (3, '1') : 3}

accepting = [3]

def fsmsim(string, current, edges, accepting):
    if string == "":
        return current in accepting
    else:
        letter = string[0]
        clave = (current, letter)
        new_current = edges.get(clave, None)
        if new_current:
            current = new_current
            string = string[1:]
            return fsmsim(string, current, edges, accepting)
        else:
            return False
{% endhighlight %}

Los autómatas finitos son sistemas formales donde la información está representada por un estado y los estados cambian
de acuerdo a las entradas. Estos autómatas sólo recuerdan una cantidad finita de información. Se usan en la verificación
de circuitos y protocolos de comunicación, en procesadores de texto, en compiladores y para describir patrones sencillos
de eventos.

El profesor Jeffrey D. Ullman es el encargado del curso de Stanford Lagunita y entre otros temas están: los lenguajes 
regulares, los autómatas determinísticos y no determinísticos, la máquina de Turing y los problemas intratables (que consumen 
mucho tiempo).
<div class="foto-center">
  <a href="https://lagunita.stanford.edu/courses/course-v1:ComputerScience+Automata+SelfPaced/about" target="_blank"><img class="img-adaptable" src="{{site.baseurl}}/imagenes/stanfordlagunita.png" alt="stanford lagunita" /></a>
  <figcaption>Cursos de Stanford Lagunita</figcaption>
</div>