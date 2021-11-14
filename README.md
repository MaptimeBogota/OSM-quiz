# OSM-quiz

This repository contain the definition of self-grading quices about OpenStreetMap knowledge.

This project is based on this quiz generator: https://github.com/UrbanInstitute/quick-quiz

In order to create a new quiz or modify the current one, you need to:

* Clone this project.

    git clone https://github.com/MaptimeBogota/OSM-quiz.git

* Change to the directory of this project.

    cd OSM-quiz

* Once in your computer, you modify the file: `osm-basic.quiz`.
You can also create another file with the `.quiz` extension and following the same syntax.

* On the command line, you call Python:

    python quiz_questions.py osm.quiz

`quiz_questions.py` is the Python script to convert your questions to a web page.

* The previous script will generate a `.josm` file.
You just need to commit both files (`.quiz` and `.json`) and push into GitHub.

    git push

* Finally, wait a little bit, until GitHub page is refreshed: [https://maptimebogota.github.io/OSM-quiz/](https://maptimebogota.github.io/OSM-quiz/).

For more information about the syntax, you can see this [syntax documentation](https://github.com/UrbanInstitute/quick-quiz#readme).


