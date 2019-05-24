simple.jsの仕様

GET
  GET http://127.0.0.1:3000/id/:Num
    -> id = :Numとなる連想配列があればそれを返す。statusCode は200
    -> id = :Numとなる連想配列がなければNot Foundを返す。statusCode は404
    例：GET http://127.0.0.1:3000/id/3
        -> {'id': 3, 'data': '3rd item'}

  GET http://127.0.0.1:3000/
    -> id = :Numとなる連想配列のリスト全体を返す。
    -> statusCode は200
    例：GET http://127.0.0.1:3000/
        -> [{'id': 0, 'data': '0th item'},
            {'id': 1, 'data': '1st item'},
            {'id': 2, 'data': '2nd item'},
            {'id': 3, 'data': '3rd item'}]

  GET http://127.0.0.1:3000/others
    適切な入力形式でないため、Bad Requestを返す。statusCode は400

DELETE
  DELETE http://127.0.0.1:3000/id/:Num
    -> id = :Numとなる連想配列があればそれを消去してOKを返す。statusCode は200
    -> id = :Numとなる連想配列がなければNot Foundを返す。statusCode は404

  DELETE http://127.0.0.1:3000/others
    適切な入力形式でないため、Bad Requestを返す。statusCode は400
