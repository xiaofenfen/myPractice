<script>
export default {
    methods: {
        // eg1
        function concat() {
            const arr = Array.prototype.slice.apply(arguments);
            arr1 = arr[0];
            arr.splice(0, 1);
            arr.forEach((item) => {
                if (Array.isArray(item)) {
                    arr1.push(...item);
                } else {
                    arr1.push(item);
                }
            });
            return arr1;
        },
        // eg2
        function concat() {
            const [
                resArr,
                ...restArr
            ] = Array.prototype.slice.apply(arguments);
            restArr.forEach((item) => {
                if (Array.isArray(item)) {
                    resArr.push(...item);
                } else {
                    resArr.push(item);
                }
            });
            return resArr;
        },
    },
};
</script>

