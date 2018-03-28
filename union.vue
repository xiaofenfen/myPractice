<script>
export default {
    methods: {
        // 只适用数字 union(union([2, 1], [4, 2], [1, 2]))
        function union() {
            const [...arr] = Array.prototype.slice.apply(arguments);
            const flatten = [].concat(...arr).sort();
            const re = [flatten[0]];
            for(var i = 1; i < flatten.length; i++){
                if( flatten[i] !== re[re.length-1]){
                    re.push(flatten[i]);
                }
            }
            return re;
        }
        // union([{a:1}, {b:1}], [{a:1}, {b:2}], [{a:1}]) => res=[{a:1}, {b:1}, {b:2}]
        // union(union([2, 1], [4, 2], [1, 2])) => res=[1,2,4]
        function union() {
            const [...arr] = Array.prototype.slice.apply(arguments);
            const flatten = [].concat(...arr);
            let obj = {}, res = [];
            flatten.forEach((item) => {
                k = JSON.stringify(item);
                if(obj[k])
                    obj[k]++;
                else
                    obj[k] = 1;
            })
            Object.keys(obj).forEach((item) => {
                res.push(JSON.parse(item));
            })
            return res;
        }
    },
};
</script>
