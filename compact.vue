<script>
export default {
    methods: {
        // eg1
        function remove(arr) {
            var result=[];
            arr.forEach((item) => {
                if (item) {
                    result.push(item);
                }
            });
            return result;
        }
    },
};
</script>
