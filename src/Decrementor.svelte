<script>
import {store} from "../store";

    const handleClick =() => {
        store.update(n => n-1)

    }
</script>
<button on:click={handleClick}>-</button>