<script setup>
import fetch from 'node-fetch';
</script>
<script>
const fetchData = ()=>{
    fetch('http://localhost:8088/products')
    .then(res => res.json())
    .then(data => console.log(data))
}



</script>