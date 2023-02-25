# Johana-Gabriela
Ejercicio: RollerDice

paquete com.ejemplo.dicerollar

importar android.media.image
importar androidx.appcompat.app.AppCompatActivity
importar android.os.Bundle
importar android.os.CountDownTimer
importar android.widget.Button
importar android.widget.ImageView
importar android.widget.TextView
importar android.widget.Toast
Importar kotlin.concurrent.timer

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)


        val btnLanzar: Button = findViewById(R.id.btnLanzar)
        btnLanzar.setOnClickListener{
            tiempo()
           // rollaDice()
        }
        rollaDice()

    }

    diversión privada  rollaDice(){
        var numero:Int=lanzar(6)
        var numero2:Int=lanzar(6)
        val txtResultado : TextView= findViewById(R.id.txtResultado)
        val txtResultado2 : TextView= findViewById(R.id.txtResultado2)
        txtResultado.text = numero.toString()
        txtResultado2.text = numero2.toString()
       // Toast.makeText(this, numero, Toast.LENGTH_LONG).show()


           val drawerResource = when(numero){
                1 -> R.drawable.dice_1
                2 -> R.drawable.dice_2
                3 -> R.drawable.dice_3
                4 -> R.drawable.dice_4
                5 -> R.drawable.dice_5
            else -> R.drawable.dice_6

        }

        val drawerResource2 = when(numero2){
            1 -> R.drawable.dice_1
            2 -> R.drawable.dice_2
            3 -> R.drawable.dice_3
            4 -> R.drawable.dice_4
            5 -> R.drawable.dice_5
            else -> R.drawable.dice_6

        }
        val imgDado:ImageView=findViewById(R.id.imgDado)
        imgDado.setImageResource(drawerResource)

        val imgDado2:ImageView=findViewById(R.id.imgDado2)
        imgDado2.setImageResource(drawerResource2)

    }

    private fun lanzar(max: Int): Int{
        Retorno (1.. max).random()
    }

    private fun tiempo(){
        object : CountDownTimer(3000, 150){

            override fun onTick(p0: Long) {
               rollaDice()
            }

            anular la diversión enFinalizar() {
            }

        }
            .start()
    }
}
