.. _customize:

Cube customization
==================

If you want to customize a cube, you can do this with a configuration file (home-directory/olapy-data/cubes/cubes-config.xml)

Here is an examples of configuration::

    <?xml version="1.0" encoding="UTF-8"?>

                <cubes>

                    <!-- if you want to set an authentication mechanism in excel so to access cube,
                        user must set a token with login url like 'http://127.0.0.1/admin  -->

                    <!-- default password = admin -->

                    <xmla_authentication>False</xmla_authentication>

                    <cube>
                        <!-- cube name => db name -->

                        <name>labster</name>

                        <!-- source : postgres | csv -->

                        <source>postgres</source>


                        <!-- star building customized star schema -->
                        <facts>

                            <!-- facts table name -->

                            <table_name>stats_line</table_name>

                            <keys>

                                <!-- ref = table_name.column  -->

                                <column_name ref="orgunit.id">departement_id</column_name>

                            </keys>

                            <!-- specify measures explicitly -->
                            <measures>

                                <!-- by default, all number type columns in facts table, or you can specify them here -->
                                <name>montant</name>
                                <name>salaire_brut_mensuel</name>
                                <name>cout_total_mensuel</name>
                            </measures>

                        </facts>
                        <!-- end building customized star schema -->


                        <!-- star building customized dimensions display in excel from the star schema -->
                        <dimensions>

                            <dimension>

                                <!-- if you want to keep the same name for excel display, just use the same name in name and displayName -->

                                <name>stats_line</name>
                                <displayName>Demande</displayName>

                                <columns>

                                    <!-- columns order matter -->
                                    <name>type_demande</name>
                                    <name>financeur</name>
                                    <name>wf_state</name>
                                    <name>type_recrutement</name>

                                </columns>

                            </dimension>

                            <dimension>

                                <!-- if you want to keep the same name for excel display, just use the same name in name and displayName -->
                                <name>orgunit</name>
                                <displayName>Organisation</displayName>

                                <columns>
                                    <!-- columns order matter -->
                                    <name>type</name>
                                    <name>nom</name>
                                    <name>sigle</name>
                                </columns>

                            </dimension>

                        </dimensions>

                        <!-- end building customized dimensions display in excel from the star schema -->


                    </cube>

                </cubes>

