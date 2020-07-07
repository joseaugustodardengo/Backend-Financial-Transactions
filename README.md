This is an application to store incoming and outgoing financial transactions, which should allow the registration and listing of these transactions.


## Requirements to run the application

  - [Node.js](https://nodejs.org/)
  - [Yarn](https://yarnpkg.com/)

## To use the project

1) You can download the project through the zip: https://github.com/joseaugustodardengo/Backend-Financial-Transactions/archive/master.zip or by cloning the repository https://github.com/joseaugustodardengo/Backend-Financial-Transactions.git
2) Access the folder where you saved the files and run the command below to run the project. This command will install the project's dependencies.
```sh
yarn
```

## Application routes
* The application runs on http://localhost/3333
* ```/transactions -> using the POST method on that route will create a transaction ``` 
* ```/transactions -> using the GET method on that route will list all transactions and the sum of the entries, withdrawals and total credit. ```

## Example of using routes
The route POST received the following elements on the **request body**.

**PS 1:** Different type of transaction income or outcome will return an error that type of transaction is not valid.

**PS 2:** If you enter a value above your balance and the type as an **outcome**, you will not be allowed to perform the operation.
```js
    {    		
	"title": "Salary",
	"value": 10000,
	"type": "income"
    }
```
The output on the screen
```js
    {   
        "id": "885dede8-b009-428e-8c39-d661977129a3",
    	"title": "Salary",
	"value": 10000,
	"type": "income"
    }
```
This route GET must return an object with the following format:
```js
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

### Techs used
* [Node.js](https://nodejs.org/en/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Express](https://expressjs.com/)
* [Nodemon](https://nodemon.io/)
* [Prettier](https://prettier.io/)
* [ESLint](https://eslint.org/)
* [Typescript](https://www.typescriptlang.org/)
