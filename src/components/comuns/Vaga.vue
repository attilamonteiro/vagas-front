<template>
    <div class="card">
        <div class="card-header bg-dark text-white">{{ titulo }}</div>
        <div class="card-body">
            <p>{{ descricao }}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">Salário: R$ {{ salario }},00 | Modalidade: {{ getModalidade }} | Tipo: {{ getTipo }} |
                Publicação:
                {{ publicacao }}</small>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Vaga',
    // props: ['titulo', 'descricao', 'salario', 'modalidade', 'tipo', 'publicacao'],
    props: {
        titulo: {
            type: String,
            required: true,
            validator(p) {
                console.log('Prop: ', p)
                if (p.length < 6) return false
                return true
            }
        },
        descricao: {
            type: String,
            // required: true,
            // default: 'Descrição não informada'
            default() {
                return '**'.repeat(5)
            }
        },
        salario: {
            type: Number,
            required: true
        },
        modalidade: {
            type: String,
            required: true
        },
        tipo: {
            type: String,
            required: true
        },
        publicacao: {
            type: String,
            required: true
        }
    },
    computed: {
        getModalidade() {
            switch (this.modalidade) {
                case 'presencial': return 'Presencial'
                case 'home-office': return 'Home Office'
            }
            return ''
        },
        getTipo() {
            switch (this.tipo) {
                case '1': return 'CLT'
                case '2': return 'PJ'
            }
            return ''
    }
}
}

</script>