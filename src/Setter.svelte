<script>
import {store} from "../store";
const handleChange = (event) => {
    store.set(event.target.value)
}
</script>
<input type="number" on:keyup={handleChange} />