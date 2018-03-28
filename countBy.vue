<script>
export default {
    methods: {
        // countBy([1,2,3,4,5,6,7], item => (item % 2 === 0)); => {false: 4, true: 3}
        // countBy([1.2, 3.5, 6.7, 1.1, 6.2], item => (Math.floor(item))); => {1:2, 3:1, 6:2}
        // countBy(['one', 'two', 'three', 'ssss'], 'length');  => {3:2, 4:1, 5:1}
        // countBy([{a: 1, b:22}, {a:2, b: 21}, {a:1, b: 12}, {a:1, b: 12}], 'a')  => {1:3, 2:1}

        function countBy(arr, func) {
            var res=[], obj = {}, k;
            if (typeof func === 'function') {
                arr.forEach((item) => {
                    res.push(func(item));
                });
                res.forEach((val) => {
                    k = val;
                    if(obj[k])
                        obj[k]++;
                    else
                        obj[k] = 1;
                })
            } else if (typeof func === 'string') {
                arr.forEach((item) => {
                    k = item[func];
                    if(obj[k])
                        obj[k]++;
                    else
                        obj[k] = 1;
                })
            }

            return obj;
        }
    },
};
</script>
