<script>
    // register hotkey K to toggle hotkey-table
    document.addEventListener('keydown', function (e) {
        if (e.keyCode === 75) {
            let hotkeyTable = document.getElementsByClassName('hotkey-table')[0];
            if (hotkeyTable.style.display === 'none') {
                hotkeyTable.style.display = 'block';
            } else {
                hotkeyTable.style.display = 'none';
            }
        }
    }, false);
</script>

<td class="hotkey-table">
    <table>
        <tr>
            <td>Play</td>
            <td>Click anywhere!</td>
        </tr>
        <tr>
            <td>Play/Pause</td>
            <td>Spacebar</td>
        </tr>
        <tr>
            <td>Live play</td>
            <td>D / Right Arrow</td>
        </tr>
        <tr>
            <td>Rewind 10 secs</td>
            <td>A / Left Arrow</td>
        </tr>
        <tr>
            <td>Volume Up</td>
            <td>W / + / Up Arrow</td>
        </tr>
        <tr>
            <td>Volume Down</td>
            <td>S / - / Down Arrow</td>
        </tr>
        <tr>
            <td>Toggle Mute</td>
            <td>M</td>
        </tr>
        <tr>
            <td>Toggle Visualization</td>
            <td>V</td>
        </tr>
        <tr>
            <td>Show FPS</td>
            <td>F</td>
        </tr>
        <tr>
            <td>Show/Hide Hotkeys</td>
            <td>K</td>
        </tr>
    </table>
</td>

<style>
    table {
        width: 100%;
        border-collapse: collapse;
    }

    /* remove some spacing under the cell */
    tr {
        line-height: 0.3em;
    }

    /* Add a grey background color to the table header and on hover */
    td {
        background-color: #383838;
        opacity: 0.8;
        text-align: center;
        border-right: 1px solid #a8a8a8; /* This creates a vertical dividing line */
    }

    /* Right-align text in the left column */
    td:nth-child(odd) {
        padding: 5px;
        text-align: right;
    }

    /* Left-align text in the right column */
    td:nth-child(even) {
        padding: 5px;

        text-align: left;
    }

    /* Remove the right border from the last cell in each row */
    td:last-child {
        border-right: none;
    }

    .hotkey-table {
        font-family: Inconsolata, monospace;
        font-weight: bolder;
        font-size: 0.75em;
    }
</style>