<template>
	<div class="backdrop" @click.self="closeModal">
		<div class="modal" :class="{ sale: theme === 'sale' }">
			<slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
		</div>
        
	</div>
</template>

<script>
export default {
	props: ["theme"],
	methods: {
		closeModal() {
			this.$emit("close");
		},
	},
};
</script>

<style>
.modal {
	width: 400px;
	padding: 20px;
	margin: 100px auto;
	background: white;
	border-radius: 10px;
}
.modal h1{
    color: rgb(21, 148, 70);
}
.backdrop {
	top: 0;
	position: fixed;
	background: rgba(0, 0, 0, 0.5);
	width: 100%;
	height: 100%;
}
.modal.sale {
	background: crimson;
}
.modal.sale h1,
.modal.sale p{
	color: white;
}

.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
}

.modal .actions a{
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    margin: 10px;
    text-decoration: none;
    border-radius: 4px;
}

.modal.sale .actions, .modal.sale .actions a{
    color: white;
}
</style>
