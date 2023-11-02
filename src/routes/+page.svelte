<script>
    let output = "";

    const Select = (value) => () => {
        output = document.querySelector(".OutputField").value;
        output += value;
    };

    const CalculateString = () => {
        try {
            output = document.querySelector(".OutputField").value;
            output = eval(output);
        } catch (error) {
            output = "Error";
        }
    };
</script>

<div class="CalculatorContainer">
    <input type="text" class="OutputField" value={output} />
    <div class="ButtonContainer">
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
        <button on:click={Select(0)} class="ZeroButton">0</button>
        <button on:click={Select(".")}>.</button>
        <button on:click={Select("/")} class="Operator">/</button>
        <button on:click={CalculateString} class="EqualButton">=</button>
    </div>
</div>

<style>
    .CalculatorContainer {
        width: 300px;
        height: 400px;
    }

    .OutputField {
        width: 100%;
    }

    button {
        width: 22%;
        margin: 1px 1%;
    }

    .buttonContainer {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }

    .Operator {
        background-color: #ff0000;
    }

    .ZeroButton {
        width: 46.5%;
    }

    .EqualButton {
        width: 100%;
    }
</style>
