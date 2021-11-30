# OSM-quiz

This repository contain the definition of self-grading quices about OpenStreetMap knowledge.

This project is based on this quiz generator: https://github.com/UrbanInstitute/quick-quiz

## Modify existing quiz

In order to modify an existing quiz, you need to:

* Clone this project.

    git clone https://github.com/MaptimeBogota/OSM-quiz.git

* Change to the directory of this project.

    cd OSM-quiz

* Once in your computer, you modify the file: `osm-basic-en.quiz` under `quices` directory.
This is the file for the basic quiz about OSM in English.
You can modify any other quiz, but this guide is made for this file.

* On the command line, you call Python:

    python quiz_questions.py quices/osm-basic-en.quiz

`quiz_questions.py` is the Python script to convert your questions to a JSON file that can be parsed as a web page.

* The previous script will generate a `.josm` file: `osm-basic-en.osm`.
You just need to commit both files (`.quiz` and `.json`) and push into GitHub.

    git commit -a -m "Quiz change"
    git push

* Finally, wait a little bit, until GitHub page is refreshed: [https://maptimebogota.github.io/OSM-quiz/](https://maptimebogota.github.io/OSM-quiz/).

For more information about the syntax, you can see this [syntax documentation](https://github.com/UrbanInstitute/quick-quiz#readme).

## Create new quiz

In order to create a new quiz, you need to:

* Clone this project.

    git clone https://github.com/MaptimeBogota/OSM-quiz.git

* Change to the directory of this project.

    cd OSM-quiz

* Create a file with the `.quiz` extension under the `quices` directory.
The content of the file should follow the syntax explained at the end.
Let's suppose you create a quiz called `myOSMquiz`, then the file should be called `myOSMquiz.quiz`

* On the command line, you call Python:

    python quiz_questions.py quices/myOSMquiz.quiz

`quiz_questions.py` is the Python script to convert your questions to a JSON file that can be parsed as a web page.

* The previous script will generate a `.josm` file: `myOSMquiz.quiz`.
First you need to add to git tracking:

    git add quices/myOSMquiz.*

* You need to create a dedicated HTML file for this quiz, calling the function quiz.
For example, called `quices/myOSMquiz.html`.
You can copy any of the existing HTML files for quices, and just replace this:

    <script>
      $(function() {
        $('#quiz').quiz("quices/myOSMquiz.json");
      });
    </script>

* Now, you need to modify the list of quices in the `index.html` file.
You just need to add a new line in the corresponding language section:

    <li><a href="myOSMquiz.html">My OSM quiz</a></li>

* You just need to commit myOSMquiz files (`.quiz`, `.json` and `.html`) the `index.html`.

    git commit quices/myOSMquiz.quiz quices/myOSMquiz.json quices/myOSMquiz.html quices/index.html -m "First commit of my own OSM quiz"

* And now you can publish into GitHub.

    git push

* Finally, wait a little bit, until GitHub page is refreshed: [https://maptimebogota.github.io/OSM-quiz/](https://maptimebogota.github.io/OSM-quiz/).

For more information about the syntax, you can see this [syntax documentation](https://github.com/UrbanInstitute/quick-quiz#readme).


# Quiz Syntax

This is the syntax for the quices:

* `//` double slash is for comments. The text in a line is not processed after these.
* `url:` the parent URL.
For quices in this page, the URL is `https://maptimebogota.github.io/OSM-quiz`.
* `#` This is the title of the quiz.
* `1)` The number of the question.
It should start from the beginning of the line.
This is the question order.
* `  - ` An invalid answer.
It should have 2 blankspaces from the beginning, and an extra blankspace after the hyphen.
* `  * ` The valida answer.
It should have 2 blankspaces from the beginning, and an extra blankspace after the hyphen.
* `  (image) XXX` An image to appear as part of the question.
XXX is the name of the image that should be in the same repository.
* `  ` A description once an answer is selected.
It pops-out when an answer is selected.
I could contain HTML tags.
