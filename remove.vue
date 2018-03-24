<script>
export default {
    methods: {
        var users = [1,2,3,4,5,6,7];

        function remove(arr, func) {
            const res = [];
            if (typeof func === 'function') {
                arr.forEach(item => {
                    if (func(item)) {
                        res.push(item);
                    }
                });
            }
            return res;
        }
        remove(users, item => (item % 2 === 0));
    },
};
</script>
