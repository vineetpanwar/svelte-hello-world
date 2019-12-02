

<div class="personalSlot">
    <header>
        <slot  name="header" /> 
    </header>
    <article>
        <slot name="body">
            <span>there is nothing to display</span>
        </slot>
    </article>
    <footer>
        <slot name="footer" />
    </footer>
</div>
<style>
    .personalSlot{
        background-color:grey;
        height:100%;
        width:100%;
    }
    </style>