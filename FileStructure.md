# Datastructure for Questions
## Requirements:
The questions have to be saved in a specific format which had to fulfill the following criteria

  * Easy to read and edit
  * Machine readable so the development team does not have to hazzle with conversion
  * Simple to export to paper

Furthermore we had to agree what kind of data we needed:

  * The question itself
  * The correct answer (could be more than one)
  * If required for the question, possible suggestions
  * For list questions the required number of correct answers
  * The type of the question (see Question Types)
  * The difficulty of the question in a ranking from 1 to 3.
  * The category to sort in the question
  * For the internal progress a status (draft, review, approved)

## Question Types

  * multipleChoice
  * fillIn
  * wildcard
  * list

## Categories
_Not finished yet_

## File format

In the end the decision for the format was to use JSON (JavaScript Object Notation), as it fulfilled the requirements in the best way.
In difference to XML it is also in file format easy to read and easy to debug. Also, as the development team decided to use JavaScript, it is the most native format.

## File structure

The file structure has been designed to follow the requirements we defined in 1.1.
```
{
  "type": "multipleChoice || fillIn || wildcard || list",
  "question": "string",
  "requiredAnswers": "int",
  "answers": [
    {
      "index": "int",
      "text": "string"
    }
  ],
  "possibilities": [
    {
      "index": "int",
      "text": "string"
    }
  ],
  "difficulty": "int(1-3)",
  "category": "Type",
  "status": "draft || review || approved"
}
```

## Exported Data

When building the questions, using the parser from the tools repo, it will create one big JSON-File with the following structure:

```
{
  "version": "Version-Number",
  "categories": {
    "categoryA": [],
    "categoryB": [],
    "categoryC": []
  }
}
```
Initially it was planned to just have one array containing all questions. After spending some thoughts about it, it became clear, that it would make more sense to order the questions by category already in the data structure.
The category-arrays will contain all approved questions as individual json object.
