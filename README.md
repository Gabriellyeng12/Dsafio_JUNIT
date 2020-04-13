# Dsafio_JUNIT
NAC1
Nome: Gabrielly Eng
RM: 83054
public class JulgamentoPrisioneiro {

private int PENA_INOCENCIA = 13;

private int PENA_CONDENACAO_MUTUA = 15;

private int PENA_CONDENACAO_INDIVIDUAL = 10;

private int PENA_CONDENACAO_CUMPLICES = 11;

public int calculaPena(Resposta respostaPrisioneiroA, Resposta respostaPrisioneiroB) {

if (respostaPrisioneiroA == Resposta.DELACAO) {

if (respostaPrisioneiroB == Resposta.DELACAO) {

return PENA_CONDENACAO_MUTUA;

} else {

return PENA_INOCENCIA;
} else {

if (respostaPrisioneiroB == Resposta.DELACAO) {

return PENA_CONDENACAO_INDIVIDUAL;

} else {

return PENA_CONDENACAO_CUMPLICES;

}

}

}

}
Criado uma classe JUNIT teste 
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class JulgamentoPrisioneiroTeste {

	@Test
	public void calculaPenaTeste() {
	int reu1 = 13;
	int reu2 = 15;
	JulgamentoPrisioneiro jp = new JulgamentoPrisioneiro();
	int resultadoEsperado = 28;
	int resultadoReal = jp.calculaPena(reu1, reu2);
			assertEquals(resultadoEsperado, resultadoReal);
	
	}

}

Foi criado uma classe enum chamada “Resposta”;
public enum Resposta {

DELACAO , PENA_INOCENCIA
}

