<script>
export default {
    methods: {
        var arr1 = [1,2,3,4,5,6,7];
        var arr2 = [1,3,4,5,8,9,10,22,1,2];
        var arr3 = [];
        arr1.forEach((item) => {
              if (!arr2.includes(item)) {
                   arr3.push(item);
              }
        });
        arr2.forEach((item) => {
            if (!arr1.includes(item)) {
                 arr3.push(item);
           }
        });
    },
};
</script>
