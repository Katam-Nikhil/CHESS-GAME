const boardElement = document.getElementById("chessboard");

if (boardElement) {
    const pieces = {
        w: {
            king: "♔",
            queen: "♕",
            rook: "♖",
            bishop: "♗",
            knight: "♘",
            pawn: "♙"
        },
        b: {
            king: "♚",
            queen: "♛",
            rook: "♜",
            bishop: "♝",
            knight: "♞",
            pawn: "♟"
        }
    };

    let board = [
        ["bR", "bN", "bB", "bQ", "bK", "bB", "bN", "bR"],
        ["bP", "bP", "bP", "bP", "bP", "bP", "bP", "bP"],
        ["", "", "", "", "", "", "", ""],
        ["", "", "", "", "", "", "", ""],
        ["", "", "", "", "", "", "", ""],
        ["", "", "", "", "", "", "", ""],
        ["wP", "wP", "wP", "wP", "wP", "wP", "wP", "wP"],
        ["wR", "wN", "wB", "wQ", "wK", "wB", "wN", "wR"]
    ];

    let currentTurn = "w";
    let selectedSquare = null;

    const turnElement = document.getElementById("turn");
    const restartButton = document.getElementById("restart");

    function pieceSymbol(piece) {
        if (!piece) return "";

        const color = piece[0];
        const type = {
            K: "king",
            Q: "queen",
            R: "rook",
            B: "bishop",
            N: "knight",
            P: "pawn"
        }[piece[1]];

        return pieces[color][type];
    }

    function drawBoard() {
        boardElement.innerHTML = "";

        for (let row = 0; row < 8; row++) {
            for (let column = 0; column < 8; column++) {
                const square = document.createElement("button");

                square.className =
                    "square " +
                    ((row + column) % 2 === 0 ? "light" : "dark");

                square.dataset.row = row;
                square.dataset.column = column;
                square.textContent = pieceSymbol(board[row][column]);

                square.addEventListener("click", () => handleClick(row, column));

                if (selectedSquare &&
                    selectedSquare.row === row &&
                    selectedSquare.column === column) {
                    square.classList.add("selected");
                }

                if (selectedSquare &&
                    isValidMove(
                        selectedSquare.row,
                        selectedSquare.column,
                        row,
                        column
                    )) {
                    square.classList.add("possible");
                }

                boardElement.appendChild(square);
            }
        }
    }

    function handleClick(row, column) {
        const piece = board[row][column];

        if (selectedSquare) {
            if (isValidMove(
                selectedSquare.row,
                selectedSquare.column,
                row,
                column
            )) {
                board[row][column] =
                    board[selectedSquare.row][selectedSquare.column];

                board[selectedSquare.row][selectedSquare.column] = "";

                // Promote pawns to queens
                if (board[row][column] === "wP" && row === 0) {
                    board[row][column] = "wQ";
                }

                if (board[row][column] === "bP" && row === 7) {
                    board[row][column] = "bQ";
                }

                selectedSquare = null;
                currentTurn = currentTurn === "w" ? "b" : "w";

                turnElement.textContent =
                    currentTurn === "w" ? "White's Turn" : "Black's Turn";
            } else {
                selectedSquare = null;

                if (piece && piece[0] === currentTurn) {
                    selectedSquare = { row, column };
                }
            }
        } else if (piece && piece[0] === currentTurn) {
            selectedSquare = { row, column };
        }

        drawBoard();
    }

    function isValidMove(fromRow, fromColumn, toRow, toColumn) {
        const piece = board[fromRow][fromColumn];

        if (!piece) return false;
        if (fromRow === toRow && fromColumn === toColumn) return false;

        const target = board[toRow][toColumn];

        if (target && target[0] === piece[0]) return false;

        const color = piece[0];
        const type = piece[1];
        const rowDifference = toRow - fromRow;
        const columnDifference = toColumn - fromColumn;

        if (type === "P") {
            const direction = color === "w" ? -1 : 1;
            const startingRow = color === "w" ? 6 : 1;

            // Move forward
            if (columnDifference === 0 &&
                !target &&
                rowDifference === direction) {
                return true;
            }

            // Move forward twice
            if (columnDifference === 0 &&
                fromRow === startingRow &&
                rowDifference === direction * 2 &&
                !board[fromRow + direction][fromColumn] &&
                !target) {
                return true;
            }

            // Capture
            if (Math.abs(columnDifference) === 1 &&
                rowDifference === direction &&
                target) {
                return true;
            }

            return false;
        }

        if (type === "N") {
            return (
                (Math.abs(rowDifference) === 2 &&
                 Math.abs(columnDifference) === 1) ||
                (Math.abs(rowDifference) === 1 &&
                 Math.abs(columnDifference) === 2)
            );
        }

        if (type === "B") {
            return Math.abs(rowDifference) === Math.abs(columnDifference) &&
                isPathClear(fromRow, fromColumn, toRow, toColumn);
        }

        if (type === "R") {
            return (
                (rowDifference === 0 || columnDifference === 0) &&
                isPathClear(fromRow, fromColumn, toRow, toColumn)
            );
        }

        if (type === "Q") {
            const straight =
                rowDifference === 0 || columnDifference === 0;

            const diagonal =
                Math.abs(rowDifference) === Math.abs(columnDifference);

            return (straight || diagonal) &&
                isPathClear(fromRow, fromColumn, toRow, toColumn);
        }

        if (type === "K") {
            return (
                Math.abs(rowDifference) <= 1 &&
                Math.abs(columnDifference) <= 1
            );
        }

        return false;
    }

    function isPathClear(fromRow, fromColumn, toRow, toColumn) {
        const rowStep =
            toRow > fromRow ? 1 : toRow < fromRow ? -1 : 0;

        const columnStep =
            toColumn > fromColumn ? 1 :
            toColumn < fromColumn ? -1 : 0;

        let row = fromRow + rowStep;
        let column = fromColumn + columnStep;

        while (row !== toRow || column !== toColumn) {
            if (board[row][column]) return false;

            row += rowStep;
            column += columnStep;
        }

        return true;
    }

    restartButton.addEventListener("click", () => {
        location.reload();
    });

    drawBoard();
}