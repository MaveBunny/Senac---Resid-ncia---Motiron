import { NextResponse } from 'next/server';
import { query } from '@/lib/db';

export async function POST(request: Request) {
  try {
    const { matricula, senha } = await request.json();

    const res = await query(
      'SELECT id, nome, matricula, tipo FROM usuario WHERE matricula = $1 AND senha = $2',
      [matricula, senha]
    );

    if (res.rows.length === 0) {
      return NextResponse.json(
        { success: false, message: 'Credenciais inválidas' },
        { status: 401 }
      );
    }

    const user = res.rows[0];

    return NextResponse.json({
      success: true,
      user: {
        id: user.id,
        nome: user.nome,
        matricula: user.matricula,
        tipo: user.tipo
      }
    });
  } catch (error) {
    console.error('Erro no login:', error);
    return NextResponse.json(
      { success: false, message: 'Erro interno do servidor' },
      { status: 500 }
    );
  }
}
