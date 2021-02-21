---
layout: page
title: Semester yang hilang dari kuliah informatikamu
---

Pas kuliah informatika (Computer Science), kamu pasti belajar banyak banget topik, mulai dari sistem operasi hingga machine learning.
Tapi ada satu hal yang biasanya gak tersentuh di kuliahmu, dan kemungkinan besar harus kamu pelajari sendiri: kemampuan menggunakan tools pada pekerjaanmu.
Nah, di sini, kami akan mengajari kamu bagaimana sih biar jago pake command line, menggunakan editor teks yang keren, menggunakan fitur-fitur mendalam dari sebuah version control system, dan yang lainnya!

<!-- Classes teach you all about advanced topics within CS, from operating systems
to machine learning, but there’s one critical subject that’s rarely covered,
and is instead left to students to figure out on their own: proficiency with
their tools. We’ll teach you how to master the command-line, use a powerful
text editor, use fancy features of version control systems, and much more! -->

Semua pelajar informatika bisa menghabiskan hingga ratusan jam menggunakan tools-tools di atas sepanjang perjalanan belajar mereka (bahkan sampai ribuan jam ketika sudah kerja), jadi sangat masuk akal kalau pas pake tools-tools di atas tuh nyaman dan enak banget. Kalau kamu bisa menguasai tools-tools yang sudah dan akan kamu gunakan di kuliah atau pekerjaanmu, kamu gak cuma bisa menghemat waktu kamu untuk menyelesaikan kerjaanatau tugasmu, tapi kamu juga bisa menyelesaikan masalah yang sebelumnya kami gak bisa selesaikan karena tingkat kompleksitasnya yang tinggi.

<!-- Students spend hundreds of hours using these tools over the course of their
education (and thousands over their career), so it makes sense to make the
experience as fluid and frictionless as possible. Mastering these tools not
only enables you to spend less time on figuring out how to bend your tools to
your will, but it also lets you solve problems that would previously seem
impossibly complex. -->

Kalau kamu penasaran dengan latar belakang dibuatnya kelas ini, bisa kamu cek [di sini](/about/).

<!-- Read about the [motivation behind this class](/about/). -->

{% comment %}
# Registration

Sign up for the IAP 2020 class by filling out this [registration form](https://forms.gle/TD1KnwCSV52qexVt9).
{% endcomment %}

<!-- # Schedule -->

# Jadwal

{% comment %}
**Lecture**: 35-225, 2pm--3pm<br>
**Office hours**: 32-G9 lounge, 3pm--4pm (every day, right after lecture)
{% endcomment %}

<ul>
{% assign lectures = site['2020'] | sort: 'date' %}
{% for lecture in lectures %}
    {% if lecture.phony != true %}
        <li>
        <strong>{{ lecture.date | date: '%-m/%d/%y' }}</strong>:
        {% if lecture.ready %}
            <a href="{{ lecture.url }}">{{ lecture.title }}</a>
        {% else %}
            {{ lecture.title }} {% if lecture.noclass %}[no class]{% endif %}
        {% endif %}
        </li>
    {% endif %}
{% endfor %}
</ul>

<!-- Video recordings of the lectures are available [on
YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J). -->

Rekaman materi-materi di kelas ini bisa kamu tonton [di
YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J).

<!-- # About the class -->

# Tentang kelas ini

**Staff**: This class is co-taught by [Anish](https://www.anishathalye.com/), [Jon](https://thesquareplanet.com/), and [Jose](http://josejg.com/).
**Questions**: Email us at [missing-semester@mit.edu](mailto:missing-semester@mit.edu).

# Beyond MIT

We've also shared this class beyond MIT in the hopes that others may
benefit from these resources. You can find posts and discussion on

 - [Hacker News](https://news.ycombinator.com/item?id=22226380)
 - [Lobsters](https://lobste.rs/s/ti1k98/missing_semester_your_cs_education_mit)
 - [/r/learnprogramming](https://www.reddit.com/r/learnprogramming/comments/eyagda/the_missing_semester_of_your_cs_education_mit/)
 - [/r/programming](https://www.reddit.com/r/programming/comments/eyagcd/the_missing_semester_of_your_cs_education_mit/)
 - [Twitter](https://twitter.com/jonhoo/status/1224383452591509507)
 - [YouTube](https://www.youtube.com/playlist?list=PLyzOVJj3bHQuloKGG59rS43e29ro7I57J)

## Acknowledgements

We thank Elaine Mello, Jim Cain, and [MIT Open
Learning](https://openlearning.mit.edu/) for making it possible for us to
record lecture videos; Anthony Zolnik and [MIT
AeroAstro](https://aeroastro.mit.edu/) for A/V equipment; and Brandi Adams and
[MIT EECS](https://www.eecs.mit.edu/) for supporting this class.

---

<div class="small center">
<p><a href="https://github.com/missing-semester/missing-semester">Source code</a>.</p>
<p>Licensed under CC BY-NC-SA.</p>
<p>See <a href="/license/">here</a> for contribution &amp; translation guidelines.</p>
</div>
