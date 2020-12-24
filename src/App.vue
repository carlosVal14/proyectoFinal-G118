<template>
<div>
  <div v-if="estado">
    <v-container>
        
            <div id="divSuperior">
                <v-toolbar class="black" >
                        
                                    <v-toolbar-title class="white--text display-1"> Ingeniería y Tecnología </v-toolbar-title>
                                    <v-spacer></v-spacer>
                                    <a href="#divInformacion" ><v-icon color="white"> info </v-icon> </a>                                
                                                    
                                    <a href="#divCasos"  color="white" class="ml-10"><v-icon color="white">favorite</v-icon></a>
                                 
                                    <v-btn color="white" fab small class="ml-10" @click.prevent="ingresar"> <v-icon> perm_identity </v-icon> </v-btn>
                            
                                
                    
                </v-toolbar>
            </div>

            <div id="divCarrusel">
                    <v-carousel :show-arrows="false">
                        <v-carousel-item   v-for="(item,i) in items"  :key="i"  :src="item.src"
                        ></v-carousel-item>
                    </v-carousel>

            </div>

            <v-container>
                <v-row justify-center>
                    <v-col xs6>
                        <h1 class="display-5 black--text"> Acerca del Reto </h1>           
                    </v-col>
                </v-row>


            </v-container>
            
            <div id="divInformacion" class="teal lighten">
               
             <v-card :loading="loading"    class="mx-auto my-12"  max-width="700">    
                <v-img src="./assets/reto.jpg">   </v-img>
                <v-card-title>Reto 118</v-card-title>
                
                <v-card-text>El neuromanagement es la aplicación de la neurociencia para la gestión exitosa en las empresas. 
                Los procesos de neuromanagement se pueden aplicar a cualquier tipo de empresa en áreas como alta dirección, 
                gestión del cambio y recursos humanos. Los resultados de implementar éste proceso se pueden apreciar en dos vertientes:
                Nivel individual y Nivel organizacional o de equipos. 

                Neuromanagement, como modelo de gestión empresarial, tiene sustento en el cerebro humano. 
                Sus ventajas son diversas, ya que impactan directamente en el rendimiento de la actividad profesional:
                Interviene en la toma de decisiones, funciona como elemento motivador, fomenta la creatividad, ayuda en la gestión del cambio, 
                iInfluye en los procesos de reclutamiento, interviene en la toma de decisiones.

</v-card-text> 
            </v-card>

            </div>

            
            <h1 class="display-5 black--text "> Casos de Exito </h1>
            <div id="divCasos" class="d-flex  teal lighten" >
                
                <v-card :loading="loading"    class="mx-auto my-12"  max-width="300">    
                    <v-img src="./assets/Avatar1.png">   </v-img>
                    <v-card-title>Caso X</v-card-title>
                    
                    <v-card-text> Gracias a Ingeniería y tecnología, logramaos predecir el comportamiento de nuestros empleados.</v-card-text> 
                </v-card>

                <v-card :loading="loading"    class="mx-auto my-12"  max-width="300">    
                    <v-img src="./assets/Avatar2.png">   </v-img>
                    <v-card-title>Caso Y</v-card-title>
                    <v-card-text> Gracias a Ingeniería y Tecnologìa logramos predecir el comportamiento de nuestros clientes.</v-card-text> 
                </v-card>

                <v-card :loading="loading"    class="mx-auto my-12"  max-width="300">    
                    <v-img src="./assets/Avatar3.png">   </v-img>
                    <v-card-title>Caso Z</v-card-title>
                    <v-card-text> Gracias a Ingeniería y Tecnología, logramos mejor nuestro ambiente empresarial.</v-card-text> 
                </v-card>
           

            </div>

            <div id=divFooter class="mt-5">
                        
                <v-footer
                    dark
                    padless
                >
                    <v-card
                    class="flex"
                    flat
                    tile
                    >
                    <v-card-title class="teal">
                        <strong class="subheading">Conéctate con nosotros en nuestras redes sociales!</strong>

                        <v-spacer></v-spacer>

                        <v-btn
                        v-for="icon in icons"
                        :key="icon"
                        class="mx-4"
                        dark
                        icon
                        >
                        <v-icon size="24px">
                            {{ icon }}
                        </v-icon>
                        </v-btn>
                    </v-card-title>

                    <v-card-text class="black white--text text-center">
                        {{ new Date().getFullYear() }} — <strong>Ingenierìa y Tecnologìa</strong>
                    </v-card-text>
                    </v-card>
                </v-footer>


            </div>

    </v-container>

  </div>
  <div v-else>
  <v-app id="app">
    <v-navigation-drawer
      v-model="drawer"
      :clipped="$vuetify.breakpoint.lgAndUp"
      app
    >
      <v-list dense>
        
        <template v-if="logueado">
          <v-list-group>
            <v-list-item slot="activator">
              <v-list-item-content>
                <v-list-item-title>
                  Almacén
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item :to="{name: 'categoria'}">
              <v-list-item-action>
                <v-icon>table_chart</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>
                  Categorías
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item :to="{name: 'articulo'}">
              <v-list-item-action>
                <v-icon>table_chart</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>
                  Artículos
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
        </template> 
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      :clipped-left="$vuetify.breakpoint.lgAndUp"
      app
      color="silver darken-3"
      dark
    >
      <v-toolbar-title
        style="width: 300px"
        class="ml-0 pl-3"
      >
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <span class="hidden-sm-and-down">Sistema</span>
      </v-toolbar-title>      
      <v-spacer></v-spacer>
      <v-btn @click="salir()" icon v-if="logueado">
        <v-icon>logout</v-icon>Salir
      </v-btn>
      <v-btn :to="{name: 'login'}" icon v-else>
        <v-icon>apps</v-icon> Login
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-container
        fluid
        fill-height
      >
        <v-slide-y-transition mode="out-in">
          <router-view/>
        </v-slide-y-transition>
      </v-container>
    </v-content>
    
            <div id=divFooter class="mt-5">
                        
                <v-footer
                    dark
                    padless
                >
                    <v-card
                    class="flex"
                    flat
                    tile
                    >
                    <v-card-title class="teal">
                        <strong class="subheading">Conéctate con nosotros en nuestras redes sociales!</strong>

                        <v-spacer></v-spacer>

                        <v-btn
                        v-for="icon in icons"
                        :key="icon"
                        class="mx-4"
                        dark
                        icon
                        >
                        <v-icon size="24px">
                            {{ icon }}
                        </v-icon>
                        </v-btn>
                    </v-card-title>

                    <v-card-text class="black white--text text-center">
                        {{ new Date().getFullYear() }} — <strong>Ingenierìa y Tecnologìa</strong>
                    </v-card-text>
                    </v-card>
                </v-footer>


            </div>
  </v-app>
  </div>
  </div>
</template>

<script>
import home from './components/home.vue'
import swal from 'sweetalert';
export default {
  components: { home },
  name: 'App',

    data () {
      return {
      drawer: false,
      estado:1,
      items: [
          {
            src: 'https://www.esic.edu/sites/default/files/2020-10/neuromanagement.jpg',
          },
          {
            src: 'https://www.iecisa.com/export/sites/web_iecisa/documents/blogs/20171003-neuromanagement.jpg',
          },
          {
            src: 'https://humancapitalsite.com/wp-content/uploads/2016/02/neuro.jpg',
          },
          {
            src: 'https://1.bp.blogspot.com/-2aTU_xMQtj0/XSBK7JXi8hI/AAAAAAAA_yQ/B1tGYky7fjs6G0k0uu7JzpA_JNKmD6zZwCLcBGAs/s1600/neuroleadership-in-a-VUCA-world.jpeg',
          },
        ],

      }
    },

  computed:{
    logueado(){
      
      return this.$store.state.usuario;
    },
  },
  created(){
    this.$store.dispatch("autoLogin");
  },
  methods:{
    salir(){
      
      this.$store.dispatch("salir");
      this.estado=1
    },

    ingresar(){
      this.estado=0
      this.$router.push('/login')
    },

    home(){
      this.estado=1
      this.$router.push('/')

    }
  }
};
</script>
