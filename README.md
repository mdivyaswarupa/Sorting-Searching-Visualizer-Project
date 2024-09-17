# Sorting-Searching-Visualizer-Project
An Interactive Tool That Efficiently Demonstrates Sorting and Searching Algorithms Through Dynamic Visual Animations, Making Complex Concepts Easy To Understand. · Created User-Friendly Controls To Enhance User Understanding and Interaction.
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Sorting and Searching Visualizer</title>

    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">

    <style>

        body {
            background-image: url('file:///home/apiiit123/Documents/mY*pRoJeCtS/3.SortVisualize Project/visualization.gif');
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-position: center center;
            color: #ffffff;
            font-family: Arial, sans-serif;
        }

        .container-fluid {
            padding: 20px;
        }

        .controls {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 15px;
            border-radius: 10px;
        }

        #bars-container {
            display: flex;
            align-items: flex-end;
            justify-content: center;
            overflow-x: auto;
            height: 400px;
            background-color: rgba(0, 0, 0, 0.5);
            border-radius: 10px;
            margin-bottom: 20px;
        }

        #bars-container div {
            margin: 0 2px;
            background-color: #17a2b8;
            text-align: center;
            color: white;
            border-radius: 3px;
        }

        .btn {
            margin-bottom: 5px;
            color: white;
        }

        .red { background-color: red !important; }
        .green { background-color: green !important; }
        .yellow { background-color: yellow !important; }
        .brown { background-color: brown !important; }

        .section-heading {
            font-size: 1.0rem;
            font-weight: bold;
            text-transform: uppercase;
            color: #ffd700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            margin-bottom: 5px;
            border-bottom: 1px solid #ffd700;
            padding-bottom: 1px;
        }

        label {
            color: #ffc107;
            text-shadow: 1px 1px 2px black;
        }

        #metrics {
            background-color: rgba(0, 0, 0, 0.7);
            padding: 10px;
            border-radius: 10px;
            margin-top: 10px;
        }

        #metrics button {
            margin-right: 10px;
            margin-bottom: 10px;
        }

        #moving-header {
            overflow: hidden;
            background-color: rgba(0, 0, 0, 0.7);
            white-space: nowrap;
            padding: 10px 0;
        }

        #moving-header h1 {
            display: inline-block;
            padding-left: 100%;
            animation: move 20s linear infinite;
            color: #ffc107;
            text-shadow: 2px 2px 4px #000000;
        }

        @keyframes move {
            0% { transform: translate(0, 0); }
            100% { transform: translate(-100%, 0); }
        }

        .left-side-buttons .btn {
            font-size: 0.8rem;
            padding: 0.4rem 0.6rem;
            margin-bottom: 5px;
            width: 100%;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .sorting-options, .searching-options, .control-options {
            margin-bottom: 20px;
        }

        .control-options .form-group {
            margin-top: 10px;
        }

        .control-options label {
            font-size: 0.8rem;
        }


        /* Individual button colors */
        #bubbleSort { background-color: #FF6B6B; border-color: #FF6B6B; }
        #selectionSort { background-color: #D8BFD8; border-color: #D8BFD8; }
        #insertionSort { background-color: #45B7D1; border-color: #45B7D1; }
        #mergeSort { background-color: #9B59B6; border-color: #9B59B6; }
        #quickSort { background-color: #3498DB; border-color: #3498DB; }
        #linearSearch { background-color: #F1C40F; border-color: #F1C40F; color: #333; }
        #binarySearch { background-color: #E67E22; border-color: #E67E22; }
        #new-array { background-color: #2ECC71; border-color: #2ECC71; }
        #pause { background-color: #E74C3C; border-color: #E74C3C; }
        #previousIteration { background-color: #95A5A6; border-color: #95A5A6; }
        #nextIteration { background-color: #34495E; border-color: #34495E; }

        #time-taken { background-color: #1ABC9C; border-color: #1ABC9C; }
        #comparisons { background-color: #D35400; border-color: #D35400; }
        #swaps { background-color: #8E44AD; border-color: #8E44AD; }
        #complexity { background-color: #27AE60; border-color: #27AE60; }
        #space-complexity { background-color: #2980B9; border-color: #2980B9; }

    </style>

</head>

<body>

    <div id="moving-header">

        <h1>Welcome to the Algorithm Visualization World.....</h1>

    </div>

    <div class="container-fluid">

        <div class="row">

            <div class="col-md-9">

                <div id="bars-container"></div>

                <div id="metrics" class="d-flex flex-wrap justify-content-between align-items-center">

                    <button class="btn btn-info btn-sm" id="time-taken">Time Taken: 0 ms</button>
                    <button class="btn btn-info btn-sm" id="comparisons">Comparisons: 0</button>
                    <button class="btn btn-info btn-sm" id="swaps">Swaps: 0</button>
                    <button class="btn btn-info btn-sm" id="complexity">Time Complexity: O(n)</button>
                    <button class="btn btn-info btn-sm" id="space-complexity">Space Complexity: O(1)</button>

                </div>

                <div class="control-options mt-3">

                    <div class="row">

                        <div class="col-md-6">

                            <div class="form-group">

                                <label for="num-bars">Number of Bars:</label>

                                <input type="range" class="form-control-range" id="num-bars" min="10" max="100" value="50">

                            </div>

                        </div>

                        <div class="col-md-6">

                            <div class="form-group">

                                <label for="sort-speed">Sorting Speed:</label>

                                <input type="range" class="form-control-range" id="sort-speed" min="1" max="100" value="50">

                            </div>

                        </div>

                    </div>

                </div>

            </div>

            <div class="col-md-3">

                <div class="controls left-side-buttons">

                    <div class="sorting-options">

                        <h5 class="section-heading">Sorting Algorithms</h5>

                        <button id="bubbleSort" class="btn btn-info btn-sm">Bubble Sort</button>
                        <button id="selectionSort" class="btn btn-info btn-sm">Selection Sort</button>
                        <button id="insertionSort" class="btn btn-info btn-sm">Insertion Sort</button>
                        <button id="mergeSort" class="btn btn-info btn-sm">Merge Sort</button>
                        <button id="quickSort" class="btn btn-info btn-sm">Quick Sort</button>

                    </div>

                    <div class="searching-options mt-3">

                        <h5 class="section-heading">Searching Algorithms</h5>

                        <button id="linearSearch" class="btn btn-warning btn-sm">Linear Search</button>
                        <button id="binarySearch" class="btn btn-warning btn-sm">Binary Search</button>

                    </div>

                    <div class="control-options mt-3">

                        <h5 class="section-heading">Control Options</h5>

                        <button id="new-array" class="btn btn-primary btn-sm">Generate New Array</button>
                        <button id="pause" class="btn btn-warning btn-sm">Pause</button>
                        <button id="previousIteration" class="btn btn-secondary btn-sm">Previous Iteration</button>
                        <button id="nextIteration" class="btn btn-secondary btn-sm">Next Iteration</button>

                    </div>

                </div>

            </div>

        </div>

    </div>

    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>

    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js"></script>

    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>

    <script>

        const barsContainer = document.getElementById('bars-container');
        const numBars = document.getElementById('num-bars');
        const sortSpeed = document.getElementById('sort-speed');
        const newArrayBtn = document.getElementById('new-array');
        const pauseBtn = document.getElementById('pause');
        const timeTakenEl = document.getElementById('time-taken');
        const comparisonsEl = document.getElementById('comparisons');
        const swapsEl = document.getElementById('swaps');
        const complexityEl = document.getElementById('complexity');
        const spaceComplexityEl = document.getElementById('space-complexity');

        let bars = [];
        let comparisons = 0;
        let swaps = 0;
        let isPaused = false;
        let startTime, endTime;
        let speed = 100;
        let iterations = [];
        let currentIteration = -1;

        function generateBars() {
            barsContainer.innerHTML = '';
            bars = [];
            const num = numBars.value;
            for (let i = 0; i < num; i++) {
                const value = Math.floor(Math.random() * 100) + 1;
                const bar = document.createElement('div');
                bar.style.height = `${value * 3}px`;
                bar.style.width = `${500 / num}px`;
                bar.setAttribute('data-value', value);
                bar.textContent = value;
                barsContainer.appendChild(bar);
                bars.push(bar);
            }
            iterations = [];
            currentIteration = -1;
            saveIteration();
        }

        function updateComplexity(timeComplexity, spaceComplexity) {
            complexityEl.textContent = `Time Complexity: ${timeComplexity}`;
            spaceComplexityEl.textContent = `Space Complexity: ${spaceComplexity}`;
        }

        function saveIteration() {
            const currentBarsState = bars.map(bar => ({
                height: bar.style.height,
                text: bar.textContent,
                value: bar.getAttribute('data-value')
            }));
            iterations.push(currentBarsState);
            currentIteration = iterations.length - 1;
        }

        function previousIteration() {
            if (currentIteration > 0) {
                currentIteration--;
                loadIteration(currentIteration);
            }
        }

        function nextIteration() {
            if (currentIteration < iterations.length - 1) {
                currentIteration++;
                loadIteration(currentIteration);
            }
        }

        function loadIteration(iterationIndex) {
            const iteration = iterations[iterationIndex];
            for (let i = 0; i < bars.length; i++) {
                bars[i].style.height = iteration[i].height;
                bars[i].textContent = iteration[i].text;
                bars[i].setAttribute('data-value', iteration[i].value);
            }
        }

        function updateSpeed() {
            speed = 1001 - sortSpeed.value * 10;
        }

        function pauseIfNeeded() {
            return new Promise(resolve => {
                if (isPaused) {
                    const interval = setInterval(() => {
                        if (!isPaused) {
                            clearInterval(interval);
                            resolve();
                        }
                    }, 100);
                } else {
                    resolve();
                }
            });
        }

        async function swap(el1, el2) {
            await new Promise(resolve => setTimeout(resolve, speed));
            const tempHeight = el1.style.height;
            el1.style.height = el2.style.height;
            el2.style.height = tempHeight;

            const tempValue = el1.textContent;
            el1.textContent = el2.textContent;
            el2.textContent = tempValue;

            const tempDataValue = el1.getAttribute('data-value');
            el1.setAttribute('data-value', el2.getAttribute('data-value'));
            el2.setAttribute('data-value', tempDataValue);

            swaps++;
            swapsEl.textContent = `Swaps: ${swaps}`;
            saveIteration();
        }

	// Implement other sorting and searching functions similarly

        async function bubbleSort() {
            startTime = performance.now();
            comparisons = 0;
            swaps = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;
            swapsEl.textContent = `Swaps: ${swaps}`;
            for (let i = 0; i < bars.length - 1; i++) {
                for (let j = 0; j < bars.length - i - 1; j++) {
                    await pauseIfNeeded();
                    bars[j].classList.add('red');
                    bars[j + 1].classList.add('red');
                    comparisons++;
                    comparisonsEl.textContent = `Comparisons: ${comparisons}`;
                    if (parseInt(bars[j].getAttribute('data-value')) > parseInt(bars[j + 1].getAttribute('data-value'))) {
                        await swap(bars[j], bars[j + 1]);
                    }
                    bars[j].classList.remove('red');
                    bars[j + 1].classList.remove('red');
                }
                bars[bars.length - i - 1].classList.add('green');
            }
            bars[0].classList.add('green');
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(n^2)', 'O(1)');
        }

        async function selectionSort() {
            startTime = performance.now();
            comparisons = 0;
            swaps = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;
            swapsEl.textContent = `Swaps: ${swaps}`;
            for (let i = 0; i < bars.length; i++) {
                let minIndex = i;
                bars[minIndex].classList.add('yellow');
                for (let j = i + 1; j < bars.length; j++) {
                    await pauseIfNeeded();
                    comparisons++;
                    comparisonsEl.textContent = `Comparisons: ${comparisons}`;
                    bars[j].classList.add('red');
                    if (parseInt(bars[j].getAttribute('data-value')) < parseInt(bars[minIndex].getAttribute('data-value'))) {
                        bars[minIndex].classList.remove('yellow');
                        minIndex = j;
                        bars[minIndex].classList.add('yellow');
                    }
                    bars[j].classList.remove('red');
                }
                if (minIndex !== i) {
                    await swap(bars[i], bars[minIndex]);
                }
                bars[minIndex].classList.remove('yellow');
                bars[i].classList.add('green');
            }
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(n^2)', 'O(1)');
        }

        async function insertionSort() {
            startTime = performance.now();
            comparisons = 0;
            swaps = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;
            swapsEl.textContent = `Swaps: ${swaps}`;
            for (let i = 1; i < bars.length; i++) {
                let key = parseInt(bars[i].getAttribute('data-value'));
                let j = i - 1;
                bars[i].classList.add('yellow');
                while (j >= 0 && parseInt(bars[j].getAttribute('data-value')) > key) {
                    await pauseIfNeeded();
                    comparisons++;
                    comparisonsEl.textContent = `Comparisons: ${comparisons}`;
                    await swap(bars[j + 1], bars[j]);
                    j = j - 1;
                }
                bars[i].classList.remove('yellow');
                bars[j + 1].classList.add('green');
            }
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(n^2)', 'O(1)');
        }

        async function mergeSort() {
            startTime = performance.now();
            comparisons = 0;
            swaps = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;
            swapsEl.textContent = `Swaps: ${swaps}`;
            await mergeSortHelper(0, bars.length - 1);
            for (let i = 0; i < bars.length; i++) {
                bars[i].classList.add('green');
            }
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(n log n)', 'O(n)');
        }

        async function mergeSortHelper(start, end) {
            if (start < end) {
                const mid = Math.floor((start + end) / 2);
                await mergeSortHelper(start, mid);
                await mergeSortHelper(mid + 1, end);
                await merge(start, mid, end);
            }
        }

               async function mergeSortHelper(left, right) {
            if (left >= right) {
                return;
            }
            const middle = Math.floor((left + right) / 2);
            await mergeSortHelper(left, middle);
            await mergeSortHelper(middle + 1, right);
            await merge(left, middle, right);
        }

        async function merge(left, middle, right) {
            let leftArr = [];
            let rightArr = [];

            for (let i = left; i <= middle; i++) {
                leftArr.push(bars[i].getAttribute('data-value'));
            }
            for (let i = middle + 1; i <= right; i++) {
                rightArr.push(bars[i].getAttribute('data-value'));
            }

            let i = 0, j = 0, k = left;
            while (i < leftArr.length && j < rightArr.length) {
                await pauseIfNeeded();
                comparisons++;
                comparisonsEl.textContent = `Comparisons: ${comparisons}`;
                if (parseInt(leftArr[i]) <= parseInt(rightArr[j])) {
                    bars[k].style.height = `${leftArr[i] * 3}px`;
                    bars[k].textContent = leftArr[i];
                    bars[k].setAttribute('data-value', leftArr[i]);
                    i++;
                } else {
                    bars[k].style.height = `${rightArr[j] * 3}px`;
                    bars[k].textContent = rightArr[j];
                    bars[k].setAttribute('data-value', rightArr[j]);
                    j++;
                }
                k++;
            }

            while (i < leftArr.length) {
                await pauseIfNeeded();
                bars[k].style.height = `${leftArr[i] * 3}px`;
                bars[k].textContent = leftArr[i];
                bars[k].setAttribute('data-value', leftArr[i]);
                i++;
                k++;
            }

            while (j < rightArr.length) {
                await pauseIfNeeded();
                bars[k].style.height = `${rightArr[j] * 3}px`;
                bars[k].textContent = rightArr[j];
                bars[k].setAttribute('data-value', rightArr[j]);
                j++;
                k++;
            }
        }

        async function merge(left, middle, right) {
    let leftArr = [];
    let rightArr = [];

    for (let i = left; i <= middle; i++) {
        leftArr.push(bars[i].getAttribute('data-value'));
    }
    for (let i = middle + 1; i <= right; i++) {
        rightArr.push(bars[i].getAttribute('data-value'));
    }

    let i = 0, j = 0, k = left;
    while (i < leftArr.length && j < rightArr.length) {
        await pauseIfNeeded();
        comparisons++;
        comparisonsEl.textContent = `Comparisons: ${comparisons}`;
        if (parseInt(leftArr[i]) <= parseInt(rightArr[j])) {
            bars[k].style.height = `${leftArr[i] * 3}px`;
            bars[k].textContent = leftArr[i];
            bars[k].setAttribute('data-value', leftArr[i]);
            i++;
        } else {
            bars[k].style.height = `${rightArr[j] * 3}px`;
            bars[k].textContent = rightArr[j];
            bars[k].setAttribute('data-value', rightArr[j]);
            j++;
        }
        k++;
    }

    while (i < leftArr.length) {
        await pauseIfNeeded();
        bars[k].style.height = `${leftArr[i] * 3}px`;
        bars[k].textContent = leftArr[i];
        bars[k].setAttribute('data-value', leftArr[i]);
        i++;
        k++;
    }

    while (j < rightArr.length) {
        await pauseIfNeeded();
        bars[k].style.height = `${rightArr[j] * 3}px`;
        bars[k].textContent = rightArr[j];
        bars[k].setAttribute('data-value', rightArr[j]);
        j++;
        k++;
    }
}

        async function quickSort() {
            startTime = performance.now();
            comparisons = 0;
            swaps = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;
            swapsEl.textContent = `Swaps: ${swaps}`;
            await quickSortHelper(0, bars.length - 1);
            for (let i = 0; i < bars.length; i++) {
                bars[i].classList.add('green');
            }
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(n log n)', 'O(log n)');
        }

        async function quickSortHelper(start, end) {
            if (start < end) {
                const pivotIndex = await partition(start, end);
                await quickSortHelper(start, pivotIndex - 1);
                await quickSortHelper(pivotIndex + 1, end);
                saveIteration();
            }
        }

        async function partition(start, end) {
            const pivotValue = parseInt(bars[end].getAttribute('data-value'));
            let pivotIndex = start;
            bars[end].classList.add('yellow');
            for (let i = start; i < end; i++) {
                await pauseIfNeeded();
                comparisons++;
                comparisonsEl.textContent = `Comparisons: ${comparisons}`;
                bars[i].classList.add('red');
                if (parseInt(bars[i].getAttribute('data-value')) < pivotValue) {
                    await swap(bars[i], bars[pivotIndex]);
                    pivotIndex++;
                }
                bars[i].classList.remove('red');
            }
            await swap(bars[pivotIndex], bars[end]);
            bars[end].classList.remove('yellow');
            return pivotIndex;
        }

        async function linearSearch() {
            const searchValue = parseInt(prompt("Enter a value to search for:"));
            startTime = performance.now();
            comparisons = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;

            for (let i = 0; i < bars.length; i++) {
                await pauseIfNeeded();
                bars[i].classList.add('yellow');
                comparisons++;
                comparisonsEl.textContent = `Comparisons: ${comparisons}`;

                if (parseInt(bars[i].getAttribute('data-value')) === searchValue) {
                    bars[i].classList.remove('yellow');
                    bars[i].classList.add('brown');
                    endTime = performance.now();
                    timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
                    updateComplexity('O(n)', 'O(1)');
                    alert(`Value ${searchValue} found at position ${i + 1}`);
                    return;
                }

                await new Promise(resolve => setTimeout(() => {
                    bars[i].classList.remove('yellow');
                    resolve();
                }, speed));
            }

            alert(`Value ${searchValue} not found!`);
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(n)', 'O(1)');
        }

        async function binarySearch() {
            // Sort the array first
            bars.sort((a, b) => parseInt(a.getAttribute('data-value')) - parseInt(b.getAttribute('data-value')));
            for (let i = 0; i < bars.length; i++) {
                bars[i].style.height = `${parseInt(bars[i].getAttribute('data-value')) * 3}px`;
            }
            saveIteration();

            const searchValue = parseInt(prompt("Enter a value to search for:"));
            startTime = performance.now();
            comparisons = 0;
            comparisonsEl.textContent = `Comparisons: ${comparisons}`;

            let left = 0;
            let right = bars.length - 1;

            while (left <= right) {
                await pauseIfNeeded();
                let mid = Math.floor((left + right) / 2);
                bars[mid].classList.add('yellow');

                comparisons++;
                comparisonsEl.textContent = `Comparisons: ${comparisons}`;

                let midValue = parseInt(bars[mid].getAttribute('data-value'));

                if (midValue === searchValue) {
                    bars[mid].classList.remove('yellow');
                    bars[mid].classList.add('brown');
                    endTime = performance.now();
                    timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
                    updateComplexity('O(log n)', 'O(1)');
                    alert(`Value ${searchValue} found at position ${mid + 1}`);
                    return;
                } else if (midValue < searchValue) {
                    left = mid + 1;
                } else {
                    right = mid - 1;
                }

                await new Promise(resolve => setTimeout(() => {
                    bars[mid].classList.remove('yellow');
                    resolve();
                }, speed));
            }

            alert(`Value ${searchValue} not found!`);
            endTime = performance.now();
            timeTakenEl.textContent = `Time Taken: ${(endTime - startTime).toFixed(2)} ms`;
            updateComplexity('O(log n)', 'O(1)');
        }

        function togglePause() {
            isPaused = !isPaused;
            pauseBtn.textContent = isPaused ? 'Resume' : 'Pause';
        }

       // Add event listeners for other sorting and searching algorithms
        newArrayBtn.addEventListener('click', generateBars);
        numBars.addEventListener('input', generateBars);
        sortSpeed.addEventListener('input', updateSpeed);
        pauseBtn.addEventListener('click', togglePause);
        document.getElementById('bubbleSort').addEventListener('click', bubbleSort);
        document.getElementById('selectionSort').addEventListener('click', selectionSort);
        document.getElementById('insertionSort').addEventListener('click', insertionSort);
        document.getElementById('mergeSort').addEventListener('click', mergeSort);
        document.getElementById('quickSort').addEventListener('click', quickSort);
        document.getElementById('linearSearch').addEventListener('click', linearSearch);
        document.getElementById('binarySearch').addEventListener('click', binarySearch);
        document.getElementById('previousIteration').addEventListener('click', previousIteration);
        document.getElementById('nextIteration').addEventListener('click', nextIteration);

        // Initialize
        generateBars();
    </script>
</body>
</html>
