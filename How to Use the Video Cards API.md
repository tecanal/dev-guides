# How to Use the Video Cards API
1. Include [Bootstrap JavaScript](https://getbootstrap.com/).
2. Include the `video-cards.js` script in your HTML file.
3. Include [Bootstrap CSS](https://getbootstrap.com/).
4. Include the `card-styles.css` sylesheet in your HTML file.
5. Create an inline script or make another JavaScript file.
6. Create an array of objects called `cards`.
7. Call `createCards(cards)`.

## Defining Cards
A card definition looks something like this:
```js
{
    timestamp: "0:02",
    type: "definition",
    data: {
        term: "Water Cycle",
        definition: "The continuous movement of water on, above, and below the surface of the Earth."
    }
}
```

All cards have a `type` field. As of right now the only two supported card types are `defintion` or `multiple_choice`.

Cards can have either a `timestamp` field or a `seconds` field if you want to keep track of time like that, but the Video Cards API automatically converts timestamps into seconds.

All cards have a `data` field but what needs to be in the `data` field depends on what type the card is.

A multiple choice card definition looks something like this:
```js
{
    timestamp: "0:05",
    type: "multiple_choice",
    data: {
        question: "Which of the following is NOT a part of the water cycle?",
        options: [
            "Condensation",
            "Carboxylation",
            "Evaporation",
            "Precipitation"
        ],
        answer: "Carboxylation"
    }
}
```

There must be at least two answer choices, but there is no maximum number of answer choices (just use good judgement). You could use this component to make True/False questions, or just normal 4-5 option multiple choice questions.

The `answer` field must be exactly equal to one of the items in the `options` array because that is how answers are checked in the Video Cards API.
