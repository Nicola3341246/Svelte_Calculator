<script>
    let output = "";

    const Select = (value) => () => {
        output = document.querySelector(".OutputField").value;
        output += value;
    };

    const Clear = () => {
        output = "";
    };

    const Backspace = () => {
        output = document.querySelector(".OutputField").value;
        output = output.substring(0, output.length - 1);
    };

    const CalculateString = () => {
        try {
            output = document.querySelector(".OutputField").value;
            output = eval(output);
        } catch (error) {
            output = "Error";
        }
    };

    document.addEventListener("keydown", function (event) {
        if (event.keyCode == 13) {
            CalculateString();
        }
    });
</script>

<div class="CalculatorContainer">
    <input type="text" class="OutputField" value={output} />
    <div class="ButtonContainer">
        <button on:click={Clear} class="DoubleWidthButton">Clear</button>
        <button on:click={Backspace} class="DoubleWidthButton">⌫</button>
        <button on:click={Select(1)}>1</button>
        <button on:click={Select(2)}>2</button>
        <button on:click={Select(3)}>3</button>
        <button on:click={Select("+")} class="Operator">+</button>
        <button on:click={Select(4)}>4</button>
        <button on:click={Select(5)}>5</button>
        <button on:click={Select(6)}>6</button>
        <button on:click={Select("-")} class="Operator">-</button>
        <button on:click={Select(7)}>7</button>
        <button on:click={Select(8)}>8</button>
        <button on:click={Select(9)}>9</button>
        <button on:click={Select("*")} class="Operator">*</button>
        <button on:click={Select(0)} class="DoubleWidthButton">0</button>
        <button on:click={Select(".")}>.</button>
        <button on:click={Select("/")} class="Operator">/</button>
        <button on:click={CalculateString} class="EqualButton">=</button>
    </div>
</div>

<style>
    .CalculatorContainer {
        width: 400px;
        height: fit-content;
        padding: 20px;
        background-color: black;
        justify-content: center;
    }

    .OutputField {
        font-size: 20px;
        text-align: center;
        width: 98%;
        padding: 1%;
        margin: 1%;
        border-radius: 5px;
        border: 0;
        background-color: gray;
    }

    button {
        width: 22%;
        height: 2rem;
        margin: 1%;
        font-size: 18px;
        border-radius: 5px;
    }

    .buttonContainer {
        height: 100%;

        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }

    .Operator {
        background-color: #ff0000;
        border-color: #cc0000;
    }

    .DoubleWidthButton {
        width: 47.33%;
    }

    .EqualButton {
        width: 100%;
        margin: 1px 0 0 0;
    }
</style>
