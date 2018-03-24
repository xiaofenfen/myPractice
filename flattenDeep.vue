<script>
export default {
    methods: {
        // Eg1
        function flattenDeep(arr, res = []) {
            arr.forEach((item) => {
                if (Array.isArray(item)) {
                    flattenDeep(item, res);
                } else {
                    res.push(item)
                }
            });
            return res;
        },
        // Eg2
        function flatten(arr) {
            return arr.reduce(function (plane, toBeFlatten) {
                return plane.concat(Array.isArray(toBeFlatten) ? flatten(toBeFlatten) : toBeFlatten);
            }, []);
        },
        // Eg3
        function flattenDepth(arr) {
            flatten = (arr)=> [].concat(...arr);
            return flatten(arr.map(x=>Array.isArray(x)? flattenDepth(x): x));
        },
    },
};
</script>
