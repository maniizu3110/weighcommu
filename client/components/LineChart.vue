<script>
import {Line} from 'vue-chartjs'
export default {
    mixins:[Line],
    props: ["chartData","options"],
    mounted(){
        this.renderChart(this.chartData,this.options)
    },
}
</script>