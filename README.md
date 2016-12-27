# LXZ_DVD_GUI
package renting2;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.io.IOException;
import java.util.ArrayList;
import javax.swing.JFrame;
import java.awt.Font;
public class DVD_RENTING_SYSTEM {
	public static void main(String[] args){
	Jframe frame=new Jframe();
	frame.setVisible(true);}
}
class Jframe extends JFrame implements ActionListener{
	
   private JMenuBar menubar;
   private JMenu menuFile,menuEdit,menuHelp;
   private JMenuItem misave,mireturn,mirenew,usehelp;
   
   
   
   
   
   
   
	JButton type_in=new JButton("新光盘录入");
	JButton old_manage=new JButton("旧，损坏光盘处理");
	JButton search=new JButton("光盘状态查询");
	JButton user_manage=new JButton("客户管理");
	JLabel i=new JLabel("DVD租赁系统");
     
	JPanel head=new JPanel();//-------------------------------------------主界面
	
	JTextField dvdname=new JTextField();
	JTextField dvdpublisher=new JTextField();
	JTextField dvdnumber=new JTextField();
	JTextField dvdquantity=new JTextField();
	JLabel name=new JLabel("DVD名称");
	JLabel quantity=new JLabel("DVD数量");
	JLabel publisher=new JLabel("DVD出版社");
	JLabel number=new JLabel("DVD编号");
	JButton enter=new JButton("录入");
	JPanel type=new JPanel();//-------------------------------------------------录入界面
	
	
	
	JTextField dvdsearch=new JTextField();
	JButton searchbutton=new JButton("DVD搜索");//-----------------------------------------搜索界面
	JPanel searchdvd=new JPanel();
	
	JTextField old_dvd=new JTextField();
	JButton oldbutton=new JButton("查询");
	JLabel old_dvd2=new JLabel("损坏光盘，损坏光盘状态查询");//------------------------------损坏光盘处理
	JPanel old_dvd1=new JPanel();
	
	
	JLabel user_manage1=new JLabel("客户管理");
	JTextField bad_user=new JTextField();
	JLabel bad_user_name=new JLabel("不良客户姓名");
	JTextField bad_user_id=new JTextField();
	JLabel bad_user_id2=new JLabel("不良客户身份证号");
	JButton bad_user_inputbutton=new JButton("添加");
	JLabel user_bad1=new JLabel("添加入客户黑名单");
	JTextField user=new JTextField();
	JLabel user_search=new JLabel("客户查询（身份证号）");
	JButton user_searchbutton=new JButton("添加");
	JPanel user_manage2=new JPanel();//-------------------------------客户管理
	

	
	
	
	public Jframe(){
		this.setLayout(new BorderLayout());
		this.setBounds(0,0,1000,700);
		this.setTitle("DVD租赁系统");
		
		menubar=new JMenuBar();
	  this.setJMenuBar(menubar);
	  menuFile=new JMenu("流程");
	  menuEdit=new JMenu("帮助");
	  menuHelp=new JMenu("反馈");
	  
	 menubar.add(menuFile);
	  menubar.add(menuEdit);
	  menubar.add(menuHelp);
	  
	  menuFile.addSeparator();
	  
	  misave=new JMenuItem("租赁流程");
	 mireturn=new JMenuItem("归还流程");
	mirenew=new JMenuItem("续借流程");
	usehelp=new JMenuItem("使用帮助");
	
	  menuFile.add(misave);
	  menuFile.add(mireturn);
	  menuFile.add(mirenew);
	menuHelp.add(usehelp);//-------------------菜单栏
	
	misave.addActionListener(this);
	mireturn.addActionListener(this);
	mirenew.addActionListener(this);
	usehelp.addActionListener(this);//------------菜单栏监听器
	
		dvdname.setEditable(true);
		dvdpublisher.setEditable(true);
		dvdnumber.setEditable(true);
		dvdquantity.setEditable(true);
		
		
		dvdsearch.setEditable(true);
		old_dvd.setEditable(true);
		bad_user.setEditable(true);
		bad_user_id.setEditable(true);
		user.setEditable(true);
		this.setLayout(null);
		
		 old_manage.setBounds(150,200,150,90);
			search.setBounds(550,200,150,90);
			user_manage.setBounds(150,400,150,90);
		type_in.setBounds(550,400,150,90);
		i.setBounds(230,30,500,100);
		i.setFont(new Font("",Font.BOLD,55));
		
		this.getContentPane().add(i);
		this.getContentPane().add(type_in);
		this.getContentPane().add(old_manage);
		this.getContentPane().add(search);
		this.getContentPane().add(user_manage);
		
	
		
	type_in.addActionListener(this);
		old_manage.addActionListener(this);
		search.addActionListener(this);
		user_manage.addActionListener(this);//------主菜单添加监听器
		
	   
		type.add(enter);
		type.add(dvdname);
		type.add(dvdpublisher);
		type.add(dvdnumber);
		type.add(dvdquantity);
		type.add(name);
		type.add(quantity);
		type.add(publisher);
		type.add(number);
		enter.addActionListener(this);//----------------录入新光盘
		type.setLayout(new GridLayout(5,5));
		
		searchdvd.add(dvdsearch);
		searchdvd.add(searchbutton);
		searchbutton.addActionListener(this);//--------搜索光盘
		
	    old_dvd1.add(old_dvd);
	    old_dvd1.add(old_dvd2);
	    old_dvd1.add(oldbutton);
	    oldbutton.addActionListener(this);//---------旧光盘处理
	
	    user_manage2.add(user_manage1);
	    user_manage2.add(bad_user);
	    user_manage2.add(bad_user_name);
	    user_manage2.add(bad_user_id);
	    user_manage2.add(bad_user_id2);
	    user_manage2.add(bad_user_inputbutton);
	    user_manage2.add(user_bad1);
	    user_manage2.add(user);
	    user_manage2.add(user_search);
	    user_manage2.add(user_searchbutton);
	    bad_user_inputbutton.addActionListener(this);
	    user_searchbutton.addActionListener(this);
	
	}
	
	public void actionPerformed(ActionEvent e) {
		if(e.getSource()==old_manage){
			this.remove(type_in);
			this.remove(old_manage);
			this.remove(i);
			this.remove(search);
			this.remove(user_manage);
			this.getContentPane().add(type,BorderLayout.NORTH);
			this.repaint();
			this.getContentPane().validate();
		}
	}
	
	
	
}
